---
title: SQL Server での認証
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 0fb92f9e854e2a7a800335390d0195243a749b33
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959975"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="44f11-102">SQL Server での認証</span><span class="sxs-lookup"><span data-stu-id="44f11-102">Authentication in SQL Server</span></span>
<span data-ttu-id="44f11-103">SQL Server は、Windows 認証モードと混合モードの 2 つの認証モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="44f11-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="44f11-104">Windows 認証は既定の認証モードです。この SQL Server セキュリティ モデルは、Windows と緊密に統合されていることから統合セキュリティと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="44f11-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="44f11-105">特定の Windows ユーザーおよび Windows グループが、信頼されたアカウントとして SQL Server へのログインが許可されます。</span><span class="sxs-lookup"><span data-stu-id="44f11-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="44f11-106">既に認証済みの Windows ユーザーは別途資格情報を提示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="44f11-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="44f11-107">混合モードは、Windows による認証と SQL Server による認証の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="44f11-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="44f11-108">SQL Server 内でユーザー名とパスワードのペアが管理されます。</span><span class="sxs-lookup"><span data-stu-id="44f11-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44f11-109">できるだけ Windows 認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44f11-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="44f11-110">Windows 認証では、暗号化された一連のメッセージを使用して SQL Server のユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="44f11-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="44f11-111">SQL Server ログインを使用した場合、SQL Server のログイン名と暗号化されたパスワードがネットワーク経由で渡されるためセキュリティが低下します。</span><span class="sxs-lookup"><span data-stu-id="44f11-111">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="44f11-112">Windows 認証では、既に Windows にログオンしているユーザーが別途 SQL Server にログオンする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="44f11-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="44f11-113">次の `SqlConnection.ConnectionString` では Windows 認証が指定されるため、ユーザー名もパスワードもユーザーに要求させません。</span><span class="sxs-lookup"><span data-stu-id="44f11-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="44f11-114">ログインは、データベース ユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="44f11-114">Logins are distinct from database users.</span></span> <span data-ttu-id="44f11-115">ログインまたは Windows グループは、別個の操作でデータベース ユーザーまたはロールにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f11-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="44f11-116">その後、ユーザーまたはロールに対してデータベース オブジェクトにアクセスするための権限を付与することになります。</span><span class="sxs-lookup"><span data-stu-id="44f11-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="44f11-117">認証シナリオ</span><span class="sxs-lookup"><span data-stu-id="44f11-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="44f11-118">通常、以下の状況では Windows 認証が最良の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="44f11-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="44f11-119">ドメイン コントローラーが存在する。</span><span class="sxs-lookup"><span data-stu-id="44f11-119">There is a domain controller.</span></span>  
  
- <span data-ttu-id="44f11-120">アプリケーションとデータベースが同じコンピューター上に存在する。</span><span class="sxs-lookup"><span data-stu-id="44f11-120">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="44f11-121">SQL Server Express または LocalDB のインスタンスを使用している。</span><span class="sxs-lookup"><span data-stu-id="44f11-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="44f11-122">次の状況では、SQL Server ログインを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="44f11-122">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="44f11-123">ワークグループが存在する。</span><span class="sxs-lookup"><span data-stu-id="44f11-123">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="44f11-124">ユーザーが別の信頼されていないドメインから接続する。</span><span class="sxs-lookup"><span data-stu-id="44f11-124">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="44f11-125">ASP.NET などのインターネットアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="44f11-125">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44f11-126">Windows 認証を指定しても、SQL Server ログインは無効になりません。</span><span class="sxs-lookup"><span data-stu-id="44f11-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="44f11-127">高い権限を持つ SQL Server ログインを無効にするには、Transact-SQL ステートメント ALTER LOGIN DISABLE を使用します。</span><span class="sxs-lookup"><span data-stu-id="44f11-127">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="44f11-128">ログインの種類</span><span class="sxs-lookup"><span data-stu-id="44f11-128">Login Types</span></span>  
 <span data-ttu-id="44f11-129">SQL Server では、次の 3 種類のログインがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="44f11-129">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="44f11-130">ローカル Windows ユーザー アカウントまたは信頼されたドメイン アカウント。</span><span class="sxs-lookup"><span data-stu-id="44f11-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="44f11-131">SQL Server が Windows に依存する形で Windows ユーザー アカウントを認証します。</span><span class="sxs-lookup"><span data-stu-id="44f11-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="44f11-132">Windows グループ。</span><span class="sxs-lookup"><span data-stu-id="44f11-132">Windows group.</span></span> <span data-ttu-id="44f11-133">Windows グループへのアクセス権を付与すると、そのグループに属しているすべての Windows ユーザー ログインにアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="44f11-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="44f11-134">SQL Server ログイン。</span><span class="sxs-lookup"><span data-stu-id="44f11-134">SQL Server login.</span></span> <span data-ttu-id="44f11-135">SQL Server はユーザー名およびパスワードのハッシュを master データベースに格納し、内部の認証方法を使ってログイン試行を検証します。</span><span class="sxs-lookup"><span data-stu-id="44f11-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44f11-136">SQL Server では、証明書または非対称キーから作成されたログインが提供されています。このログインはコード署名にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="44f11-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="44f11-137">SQL Server への接続には使用できません。</span><span class="sxs-lookup"><span data-stu-id="44f11-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="44f11-138">混合モード認証</span><span class="sxs-lookup"><span data-stu-id="44f11-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="44f11-139">混合モード認証を使用する場合は、SQL Server に格納される SQL Server ログインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f11-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="44f11-140">さらに、SQL Server のユーザー名とパスワードを実行時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f11-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44f11-141">SQL Server をインストールすると、`sa` ("system administrator" の略) という名前の SQL Server ログインが作成されます。</span><span class="sxs-lookup"><span data-stu-id="44f11-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="44f11-142">`sa` ログインには強力なパスワードを割り当て、アプリケーションで `sa` ログインを使用することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="44f11-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="44f11-143">`sa` ログインは、サーバー全体に対する取り消し不可能な管理者の資格情報を持つ `sysadmin` 固定サーバー ロールにマップされます。</span><span class="sxs-lookup"><span data-stu-id="44f11-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="44f11-144">システム管理者のアクセス権が攻撃者によって取得された場合の潜在的な損害は計り知れません。</span><span class="sxs-lookup"><span data-stu-id="44f11-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="44f11-145">既定では、Windows `BUILTIN\Administrators` グループ (ローカル管理者のグループ) のすべてのメンバーが `sysadmin` ロールに所属しますが、sysadmin ロールから Windows の Administrators グループのメンバーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="44f11-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="44f11-146">SQL Server には、SQL Server ログインの Windows パスワードポリシーメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="44f11-146">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="44f11-147">パスワードの複雑性のポリシーは、考えられるパスワードの数を増やすことにより、総当たり攻撃を防ぐようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="44f11-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="44f11-148">SQL Server は、SQL Server 内で使用されるパスワードと同じ複雑さと有効期限ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="44f11-148">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44f11-149">ユーザー入力から文字列を連結することによって接続文字列を構築している場合、接続文字列のインジェクション攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="44f11-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="44f11-150"><xref:System.Data.SqlClient.SqlConnectionStringBuilder> を使用すると、構文的に正しい接続文字列を実行時に作成できます。</span><span class="sxs-lookup"><span data-stu-id="44f11-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="44f11-151">詳細については、「[接続文字列ビルダー](../connection-string-builders.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44f11-151">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="44f11-152">外部資料</span><span class="sxs-lookup"><span data-stu-id="44f11-152">External Resources</span></span>  
 <span data-ttu-id="44f11-153">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44f11-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="44f11-154">Resource</span><span class="sxs-lookup"><span data-stu-id="44f11-154">Resource</span></span>|<span data-ttu-id="44f11-155">説明</span><span class="sxs-lookup"><span data-stu-id="44f11-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="44f11-156">プリンシパル</span><span class="sxs-lookup"><span data-stu-id="44f11-156">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="44f11-157">SQL Server のログインおよびその他のセキュリティ プリンシパルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44f11-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44f11-158">参照</span><span class="sxs-lookup"><span data-stu-id="44f11-158">See also</span></span>

- [<span data-ttu-id="44f11-159">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="44f11-159">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="44f11-160">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="44f11-160">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="44f11-161">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="44f11-161">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="44f11-162">接続文字列</span><span class="sxs-lookup"><span data-stu-id="44f11-162">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="44f11-163">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="44f11-163">ADO.NET Overview</span></span>](../ado-net-overview.md)
