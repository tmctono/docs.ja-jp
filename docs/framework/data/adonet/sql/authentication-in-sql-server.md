---
title: SQL Server での認証
description: Windows 認証モードや混合モードなど、ADO.NET の SQL Server での認証について説明します。
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: e9915598acfbdefb59069d6a9c6ef4b7c824e4c6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286547"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="c41c6-103">SQL Server での認証</span><span class="sxs-lookup"><span data-stu-id="c41c6-103">Authentication in SQL Server</span></span>
<span data-ttu-id="c41c6-104">SQL Server は、Windows 認証モードと混合モードの 2 つの認証モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-104">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="c41c6-105">Windows 認証は既定の認証モードです。この SQL Server セキュリティ モデルは、Windows と緊密に統合されていることから統合セキュリティと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-105">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="c41c6-106">特定の Windows ユーザー アカウントとグループ アカウントは、SQL Server へのログインが信頼されています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-106">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="c41c6-107">すでに認証されている Windows ユーザーは、追加の資格情報を提示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-107">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="c41c6-108">混合モードは、Windows による認証と SQL Server による認証の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-108">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="c41c6-109">SQL Server 内でユーザー名とパスワードのペアが管理されます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-109">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c41c6-110">可能な限り、Windows 認証を使用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-110">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="c41c6-111">Windows 認証では、暗号化された一連のメッセージを使用して SQL Server のユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-111">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="c41c6-112">SQL Server ログインを使用した場合、SQL Server のログイン名と暗号化されたパスワードがネットワーク経由で渡されるためセキュリティが低下します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-112">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="c41c6-113">Windows 認証では、既に Windows にログオンしているユーザーが別途 SQL Server にログオンする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-113">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="c41c6-114">次の `SqlConnection.ConnectionString` では Windows 認証が指定されるため、ユーザー名もパスワードもユーザーに要求させません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-114">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="c41c6-115">ログインはデータベース ユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-115">Logins are distinct from database users.</span></span> <span data-ttu-id="c41c6-116">ログインまたは Windows グループは、別の操作でデータベース ユーザーまたはロールにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-116">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="c41c6-117">その後、ユーザーまたはロールに対してデータベース オブジェクトにアクセスするための権限を付与することになります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-117">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="c41c6-118">認証のシナリオ</span><span class="sxs-lookup"><span data-stu-id="c41c6-118">Authentication Scenarios</span></span>  
 <span data-ttu-id="c41c6-119">通常、以下の状況では Windows 認証が最良の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="c41c6-119">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="c41c6-120">ドメイン コントローラーがある。</span><span class="sxs-lookup"><span data-stu-id="c41c6-120">There is a domain controller.</span></span>  
  
- <span data-ttu-id="c41c6-121">アプリケーションとデータベースが同じコンピューター上にある。</span><span class="sxs-lookup"><span data-stu-id="c41c6-121">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="c41c6-122">SQL Server Express または LocalDB のインスタンスを使用している。</span><span class="sxs-lookup"><span data-stu-id="c41c6-122">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="c41c6-123">SQL Server のログインは、次の状況でよく使われます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-123">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="c41c6-124">ワークグループがある場合。</span><span class="sxs-lookup"><span data-stu-id="c41c6-124">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="c41c6-125">ユーザーが、信頼されていない別のドメインから接続する。</span><span class="sxs-lookup"><span data-stu-id="c41c6-125">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="c41c6-126">ASP.NET などのインターネット アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c41c6-126">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c41c6-127">Windows 認証を指定しても、SQL Server ログインは無効になりません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-127">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="c41c6-128">高い権限を持つ SQL Server ログインを無効にするには、Transact-SQL ステートメント ALTER LOGIN DISABLE を使用します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-128">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="c41c6-129">ログインの種類</span><span class="sxs-lookup"><span data-stu-id="c41c6-129">Login Types</span></span>  
 <span data-ttu-id="c41c6-130">SQL Server では、次の 3 種類のログインがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-130">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="c41c6-131">ローカル Windows ユーザー アカウントまたは信頼される側のドメイン アカウント。</span><span class="sxs-lookup"><span data-stu-id="c41c6-131">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="c41c6-132">SQL Server が Windows に依存する形で Windows ユーザー アカウントを認証します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-132">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="c41c6-133">Windows グループ。</span><span class="sxs-lookup"><span data-stu-id="c41c6-133">Windows group.</span></span> <span data-ttu-id="c41c6-134">Windows グループへのアクセス権を付与すると、そのグループのメンバーであるすべての Windows ユーザー ログインへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-134">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="c41c6-135">SQL Server ログイン。</span><span class="sxs-lookup"><span data-stu-id="c41c6-135">SQL Server login.</span></span> <span data-ttu-id="c41c6-136">SQL Server はユーザー名およびパスワードのハッシュを master データベースに格納し、内部の認証方法を使ってログイン試行を検証します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-136">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c41c6-137">SQL Server では、証明書または非対称キーから作成されたログインが提供されています。このログインはコード署名にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-137">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="c41c6-138">SQL Server への接続には使用できません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-138">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="c41c6-139">混合モード認証</span><span class="sxs-lookup"><span data-stu-id="c41c6-139">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="c41c6-140">混合モード認証を使用する場合は、SQL Server に格納される SQL Server ログインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-140">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="c41c6-141">さらに、SQL Server のユーザー名とパスワードを実行時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-141">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c41c6-142">SQL Server は、`sa` ("system administrator" の略) という名前の SQL Server ログインでインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-142">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="c41c6-143">`sa` ログインに強力なパスワードを割り当て、アプリケーションで `sa` ログインを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c41c6-143">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="c41c6-144">`sa` ログインは `sysadmin` 固定サーバー ロールにマップされます。このロールには、サーバー全体に対する取り消し不可能な管理者資格情報が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-144">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="c41c6-145">攻撃者がシステム管理者としてアクセス権を獲得した場合、損害の可能性はとどまることがありません。</span><span class="sxs-lookup"><span data-stu-id="c41c6-145">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="c41c6-146">既定では、Windows `BUILTIN\Administrators` グループ (ローカル管理者のグループ) のすべてのメンバーが `sysadmin` ロールに所属しますが、sysadmin ロールから Windows の Administrators グループのメンバーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-146">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="c41c6-147">SQL Server では、SQL Server ログインのための Windows パスワード ポリシー メカニズムが提供されています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-147">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="c41c6-148">パスワードの複雑性のポリシーは、考えられるパスワードの数を増やすことにより、総当たり攻撃を防ぐようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="c41c6-148">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="c41c6-149">SQL Server では、SQL Server 内部で使用されるパスワードに、同じ複雑性ポリシーおよび有効期限ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-149">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c41c6-150">ユーザー入力から文字列を連結することによって接続文字列を構築している場合、接続文字列のインジェクション攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="c41c6-150">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="c41c6-151"><xref:System.Data.SqlClient.SqlConnectionStringBuilder> を使用すると、構文的に正しい接続文字列を実行時に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c41c6-151">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="c41c6-152">詳細については、「[接続文字列ビルダー](../connection-string-builders.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c41c6-152">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c41c6-153">外部リソース</span><span class="sxs-lookup"><span data-stu-id="c41c6-153">External Resources</span></span>  
 <span data-ttu-id="c41c6-154">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c41c6-154">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="c41c6-155">リソース</span><span class="sxs-lookup"><span data-stu-id="c41c6-155">Resource</span></span>|<span data-ttu-id="c41c6-156">説明</span><span class="sxs-lookup"><span data-stu-id="c41c6-156">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="c41c6-157">プリンシパル</span><span class="sxs-lookup"><span data-stu-id="c41c6-157">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="c41c6-158">SQL Server のログインおよびその他のセキュリティ プリンシパルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c41c6-158">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c41c6-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c41c6-159">See also</span></span>

- [<span data-ttu-id="c41c6-160">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c41c6-160">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="c41c6-161">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c41c6-161">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="c41c6-162">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="c41c6-162">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="c41c6-163">接続文字列</span><span class="sxs-lookup"><span data-stu-id="c41c6-163">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="c41c6-164">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c41c6-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
