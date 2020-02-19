---
title: SQL Server でのストアド プロシージャの署名
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 0131655d06a6ef543ea460d04739401538cac04b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452358"
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="c0666-102">SQL Server でのストアド プロシージャの署名</span><span class="sxs-lookup"><span data-stu-id="c0666-102">Signing Stored Procedures in SQL Server</span></span>

<span data-ttu-id="c0666-103">デジタル署名は、署名者の秘密キーで暗号化されたデータ ダイジェストです。</span><span class="sxs-lookup"><span data-stu-id="c0666-103">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="c0666-104">秘密キーにより、デジタル署名がその保持者または所有者に固有であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="c0666-104">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="c0666-105">ストアドプロシージャ、関数 (インラインテーブル値関数を除く)、トリガー、およびアセンブリに署名できます。</span><span class="sxs-lookup"><span data-stu-id="c0666-105">You can sign stored procedures, functions (except for inline table-valued functions), triggers, and assemblies.</span></span>

<span data-ttu-id="c0666-106">証明書や非対称キーを使用してストアド プロシージャに署名することができます。</span><span class="sxs-lookup"><span data-stu-id="c0666-106">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="c0666-107">この機能は、動的 SQL などのように、組み合わせ所有権によって権限を継承できない場合や、組み合わせ所有権が壊れている場合を想定して用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0666-107">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="c0666-108">その後、証明書にマップされたユーザーを作成し、ストアドプロシージャがアクセスする必要があるオブジェクトに対する権限をユーザーに付与することができます。</span><span class="sxs-lookup"><span data-stu-id="c0666-108">You can then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>

<span data-ttu-id="c0666-109">同じ証明書にマップされたログインを作成し、そのログインに必要なサーバーレベルの権限を付与したり、1つ以上の固定サーバーロールにログインを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c0666-109">You can also create a login mapped to the same certificate, and then grant any necessary server-level permissions to that login, or add the login to one or more of the fixed server roles.</span></span> <span data-ttu-id="c0666-110">これは、高いレベルのアクセス許可が必要なシナリオに対して `TRUSTWORTHY` データベース設定を有効にしないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c0666-110">This is designed to avoid enabling the `TRUSTWORTHY` database setting for scenarios in which higher level permissions are needed.</span></span>

<span data-ttu-id="c0666-111">ストアドプロシージャを実行すると、SQL Server は、証明書ユーザーの権限またはログインを呼び出し元の権限と結合します。</span><span class="sxs-lookup"><span data-stu-id="c0666-111">When the stored procedure is executed, SQL Server combines the permissions of the certificate user and/or login with those of the caller.</span></span> <span data-ttu-id="c0666-112">`EXECUTE AS` 句とは異なり、プロシージャの実行コンテキストは変更されません。</span><span class="sxs-lookup"><span data-stu-id="c0666-112">Unlike the `EXECUTE AS` clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="c0666-113">ログイン名とユーザー名を返す組み込み関数を実行すると、証明書ユーザーの名前ではなく、呼び出し元の名前が返されます。</span><span class="sxs-lookup"><span data-stu-id="c0666-113">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>

## <a name="creating-certificates"></a><span data-ttu-id="c0666-114">証明書の作成</span><span class="sxs-lookup"><span data-stu-id="c0666-114">Creating Certificates</span></span>

<span data-ttu-id="c0666-115">証明書または非対称キーを使用してストアドプロシージャに署名すると、ストアドプロシージャコードの暗号化されたハッシュで構成されるデータダイジェストが、execute as ユーザーと共に、秘密キーを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0666-115">When you sign a stored procedure with a certificate or asymmetric key, a data digest consisting of the encrypted hash of the stored procedure code, along with the execute-as user, is created using the private key.</span></span> <span data-ttu-id="c0666-116">実行時に、このデータ ダイジェストが公開キーを使用して復号化され、ストアド プロシージャのハッシュ値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="c0666-116">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="c0666-117">実行ユーザーを変更すると、デジタル署名が一致しなくなるようにハッシュ値が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c0666-117">Changing the execute-as user invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="c0666-118">ストアドプロシージャを変更すると、署名が完全に削除されます。これにより、秘密キーへのアクセス権を持たないユーザーは、ストアドプロシージャコードを変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c0666-118">Modifying the stored procedure drops the signature entirely, which prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="c0666-119">どちらの場合も、コードまたは実行ユーザーを変更するたびに、プロシージャに再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0666-119">In either case, you must re-sign the procedure each time you change the code or the execute-as user.</span></span>

<span data-ttu-id="c0666-120">モジュールに署名するには、次の2つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0666-120">There are two required steps involved in signing a module:</span></span>

1. <span data-ttu-id="c0666-121">Transact-SQL ステートメント `CREATE CERTIFICATE [certificateName]` を使用して、証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0666-121">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="c0666-122">このステートメントには、開始日、終了日、パスワードを設定するためのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c0666-122">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="c0666-123">既定の有効期限は1年です。</span><span class="sxs-lookup"><span data-stu-id="c0666-123">The default expiration date is one year.</span></span>

1. <span data-ttu-id="c0666-124">Transact-SQL ステートメント `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` を使用して、証明書によってプロシージャに署名します。</span><span class="sxs-lookup"><span data-stu-id="c0666-124">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>

<span data-ttu-id="c0666-125">モジュールに署名したら、証明書に関連付けられている追加のアクセス許可を保持するために、1つまたは複数のプリンシパルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0666-125">Once the module has been signed, one or more principals needs to be created in order to hold the additional permissions that should be associated with the certificate.</span></span>

<span data-ttu-id="c0666-126">モジュールにデータベースレベルの権限を追加する必要がある場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c0666-126">If the module needs additional database-level permissions:</span></span>

1. <span data-ttu-id="c0666-127">Transact-SQL ステートメント `CREATE USER [userName] FROM CERTIFICATE [certificateName]` を使用して、証明書に関連付けられたデータベース ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0666-127">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="c0666-128">このユーザーはデータベースにのみ存在し、ログインに関連付けられていません。ただし、同じ証明書からログインを作成した場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="c0666-128">This user exists in the database only and is not associated with a login unless a login has also been created from that same certificate.</span></span>

1. <span data-ttu-id="c0666-129">証明書ユーザーに必要なデータベースレベルのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c0666-129">Grant the certificate user the required database-level permissions.</span></span>

<span data-ttu-id="c0666-130">モジュールに追加のサーバーレベルのアクセス許可が必要な場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c0666-130">If the module needs additional server-level permissions:</span></span>

1. <span data-ttu-id="c0666-131">証明書を `master` データベースにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c0666-131">Copy the certificate to the `master` database.</span></span>

1. <span data-ttu-id="c0666-132">Transact-sql `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` ステートメントを使用して、その証明書に関連付けられたログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0666-132">Create a login associated with that certificate using the Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` statement.</span></span>

1. <span data-ttu-id="c0666-133">証明書のログインに必要なサーバーレベルの権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="c0666-133">Grant the certificate login the required server-level permissions.</span></span>

> [!NOTE]
> <span data-ttu-id="c0666-134">証明書では、DENY ステートメントを使用して権限が取り消されているユーザーに権限を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="c0666-134">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="c0666-135">DENY は常に GRANT よりも優先されるため、証明書ユーザーに許可された権限を呼び出し元が継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0666-135">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>

## <a name="external-resources"></a><span data-ttu-id="c0666-136">外部資料</span><span class="sxs-lookup"><span data-stu-id="c0666-136">External Resources</span></span>

<span data-ttu-id="c0666-137">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0666-137">For more information, see the following resources.</span></span>

|<span data-ttu-id="c0666-138">リソース</span><span class="sxs-lookup"><span data-stu-id="c0666-138">Resource</span></span>|<span data-ttu-id="c0666-139">説明</span><span class="sxs-lookup"><span data-stu-id="c0666-139">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="c0666-140">[モジュール署名](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="c0666-140">[Module Signing](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))</span></span>|<span data-ttu-id="c0666-141">モジュール署名について説明します。サンプルシナリオと、関連する Transact-sql 記事へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0666-141">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL articles.</span></span>|
|[<span data-ttu-id="c0666-142">証明書を使用したストアド プロシージャへの署名</span><span class="sxs-lookup"><span data-stu-id="c0666-142">Signing Stored Procedures with a Certificate</span></span>](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|<span data-ttu-id="c0666-143">証明書を使用したストアド プロシージャの署名のチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="c0666-143">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c0666-144">参照</span><span class="sxs-lookup"><span data-stu-id="c0666-144">See also</span></span>

- [<span data-ttu-id="c0666-145">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c0666-145">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="c0666-146">SQL Server セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="c0666-146">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="c0666-147">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c0666-147">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="c0666-148">SQL Server でのストアド プロシージャを使用したアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="c0666-148">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="c0666-149">SQL Server での安全な動的 SQL の作成</span><span class="sxs-lookup"><span data-stu-id="c0666-149">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="c0666-150">SQL Server での借用を使用したアクセス許可のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c0666-150">Customizing Permissions with Impersonation in SQL Server</span></span>](customizing-permissions-with-impersonation-in-sql-server.md)
- [<span data-ttu-id="c0666-151">ストアド プロシージャでのデータの変更</span><span class="sxs-lookup"><span data-stu-id="c0666-151">Modifying Data with Stored Procedures</span></span>](../modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="c0666-152">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c0666-152">ADO.NET Overview</span></span>](../ado-net-overview.md)
