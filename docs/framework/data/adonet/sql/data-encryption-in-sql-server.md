---
title: SQL Server でのデータの暗号化
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: d0bda11f1a2933d096aa91d2be79d3af35172284
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169532"
---
# <a name="data-encryption-in-sql-server"></a><span data-ttu-id="ce331-102">SQL Server でのデータの暗号化</span><span class="sxs-lookup"><span data-stu-id="ce331-102">Data Encryption in SQL Server</span></span>

<span data-ttu-id="ce331-103">SQL Server には、証明書、非対称キー、対称キーのいずれかを使ってデータを暗号化したり、復号化したりできる関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ce331-103">SQL Server provides functions to encrypt and decrypt data using a certificate, asymmetric key, or symmetric key.</span></span> <span data-ttu-id="ce331-104">これらはすべて内部の証明書ストアで管理されます。</span><span class="sxs-lookup"><span data-stu-id="ce331-104">It manages all of these in an internal certificate store.</span></span> <span data-ttu-id="ce331-105">証明書ストアは、1 つ上の層がその下の層を保護する暗号化階層を使用することによって、証明書およびキーを保護します。</span><span class="sxs-lookup"><span data-stu-id="ce331-105">The store uses an encryption hierarchy that secures certificates and keys at one level with the layer above it in the hierarchy.</span></span> <span data-ttu-id="ce331-106">SQL Server では、この機能領域をシークレット ストレージと呼びます。</span><span class="sxs-lookup"><span data-stu-id="ce331-106">This feature area of SQL Server is called Secret Storage.</span></span>  
  
 <span data-ttu-id="ce331-107">暗号化関数によってサポートされる最速の暗号化方式は対称キーによる暗号化です。</span><span class="sxs-lookup"><span data-stu-id="ce331-107">The fastest mode of encryption supported by the encryption functions is symmetric key encryption.</span></span> <span data-ttu-id="ce331-108">この方法は大量のデータを処理する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="ce331-108">This mode is suitable for handling large volumes of data.</span></span> <span data-ttu-id="ce331-109">対称キーは、証明書、パスワードまたは他の対称キーで暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="ce331-109">The symmetric keys can be encrypted by certificates, passwords or other symmetric keys.</span></span>  
  
## <a name="keys-and-algorithms"></a><span data-ttu-id="ce331-110">キーとアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="ce331-110">Keys and Algorithms</span></span>  

 <span data-ttu-id="ce331-111">SQL Server は、DES、Triple DES、RC2、RC4、128 ビット RC4、DESX、128 ビット AES、192 ビット AES、256 ビット AES など、複数の対称キー暗号化アルゴリズムをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ce331-111">SQL Server supports several symmetric key encryption algorithms, including DES, Triple DES, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span> <span data-ttu-id="ce331-112">アルゴリズムは Windows Crypto API を使って実装されています。</span><span class="sxs-lookup"><span data-stu-id="ce331-112">The algorithms are implemented using the Windows Crypto API.</span></span>  
  
 <span data-ttu-id="ce331-113">SQL Server は、オープンする対称キーをデータベース接続のスコープ内で複数管理できます。</span><span class="sxs-lookup"><span data-stu-id="ce331-113">Within the scope of a database connection, SQL Server can maintain multiple open symmetric keys.</span></span> <span data-ttu-id="ce331-114">オープンするキーは証明書ストアから取得でき、データを復号化する際に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce331-114">An open key is retrieved from the store and is available for decrypting data.</span></span> <span data-ttu-id="ce331-115">データの一部が復号化されていれば、使用する対称キーを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ce331-115">When a piece of data is decrypted, there is no need to specify the symmetric key to use.</span></span> <span data-ttu-id="ce331-116">暗号化された各値は、どのキーを使って暗号化されたかを示すキー識別子 (キー GUID) を保持します。</span><span class="sxs-lookup"><span data-stu-id="ce331-116">Each encrypted value contains the key identifier (key GUID) of the key used to encrypt it.</span></span> <span data-ttu-id="ce331-117">正しいキーが復号化されてオープンされた場合、暗号化されたバイト ストリームとオープンする対称キーとがエンジンによって照合されます。</span><span class="sxs-lookup"><span data-stu-id="ce331-117">The engine matches the encrypted byte stream to an open symmetric key, if the correct key has been decrypted and is open.</span></span> <span data-ttu-id="ce331-118">次に、このキーを使って復号化が実行されて、データが返されます。</span><span class="sxs-lookup"><span data-stu-id="ce331-118">This key is then used to perform decryption and return the data.</span></span> <span data-ttu-id="ce331-119">正しいキーがオープンされなかった場合は NULL が返されます。</span><span class="sxs-lookup"><span data-stu-id="ce331-119">If the correct key is not open, NULL is returned.</span></span>  
  
 <span data-ttu-id="ce331-120">データベース内の暗号化されたデータを使用する方法がわかる例については、「[データの列の暗号化](/sql/relational-databases/security/encryption/encrypt-a-column-of-data)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce331-120">For an example that shows how to work with encrypted data in a database, see [Encrypt a Column of Data](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).</span></span>
  
## <a name="external-resources"></a><span data-ttu-id="ce331-121">外部リソース</span><span class="sxs-lookup"><span data-stu-id="ce331-121">External Resources</span></span>  

 <span data-ttu-id="ce331-122">データの暗号化の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce331-122">For more information on data encryption, see the following resources.</span></span>  
  
|<span data-ttu-id="ce331-123">リソース</span><span class="sxs-lookup"><span data-stu-id="ce331-123">Resource</span></span>|<span data-ttu-id="ce331-124">説明</span><span class="sxs-lookup"><span data-stu-id="ce331-124">Description</span></span>|  
|-|-|  
|[<span data-ttu-id="ce331-125">SQL Server の暗号化</span><span class="sxs-lookup"><span data-stu-id="ce331-125">SQL Server Encryption</span></span>](/sql/relational-databases/security/encryption/sql-server-encryption)|<span data-ttu-id="ce331-126">SQL Server における暗号化の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="ce331-126">Provides an overview of encryption in SQL Server.</span></span> <span data-ttu-id="ce331-127">このトピックには、他の記事へのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce331-127">This topic includes links to additional articles.</span></span>|  
|[<span data-ttu-id="ce331-128">暗号化階層</span><span class="sxs-lookup"><span data-stu-id="ce331-128">Encryption Hierarchy</span></span>](/sql/relational-databases/security/encryption/encryption-hierarchy)|<span data-ttu-id="ce331-129">SQL Server における暗号化の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="ce331-129">Provides an overview of encryption in SQL Server.</span></span> <span data-ttu-id="ce331-130">このトピックでは、他の記事へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ce331-130">This topic provides links to additional articles.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce331-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce331-131">See also</span></span>

- [<span data-ttu-id="ce331-132">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ce331-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="ce331-133">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="ce331-133">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="ce331-134">SQL Server での認証</span><span class="sxs-lookup"><span data-stu-id="ce331-134">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="ce331-135">SQL Server のサーバー ロールとデータベース ロール</span><span class="sxs-lookup"><span data-stu-id="ce331-135">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)
- [<span data-ttu-id="ce331-136">SQL Server における所有権とユーザーとスキーマの分離</span><span class="sxs-lookup"><span data-stu-id="ce331-136">Ownership and User-Schema Separation in SQL Server</span></span>](ownership-and-user-schema-separation-in-sql-server.md)
- [<span data-ttu-id="ce331-137">SQL Server の承認とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce331-137">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="ce331-138">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ce331-138">ADO.NET Overview</span></span>](../ado-net-overview.md)
