---
title: メンバーシップとロール プロバイダー
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: b5cb743fb3533d2f3a8016c9357d6ead498a5878
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756118"
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="958d1-102">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="958d1-102">Membership and Role Provider</span></span>
<span data-ttu-id="958d1-103">メンバーシップとロール プロバイダーのサンプルでは、サービスが [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] メンバーシップとロール プロバイダーを使用してクライアントを認証および承認するための方法を示します。</span><span class="sxs-lookup"><span data-stu-id="958d1-103">The Membership and Role Provider sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="958d1-104">この例では、クライアントはコンソール アプリケーション (.exe) であり、サービスはインターネット インフォメーション サービス (IIS) によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="958d1-104">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="958d1-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958d1-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="958d1-106">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="958d1-106">The sample demonstrates how:</span></span>  
  
- <span data-ttu-id="958d1-107">クライアントがユーザー名とパスワードの組み合わせを使用して認証する。</span><span class="sxs-lookup"><span data-stu-id="958d1-107">A client can authenticate by using the username-password combination.</span></span>  
  
- <span data-ttu-id="958d1-108">サーバーがクライアント資格情報を [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] メンバーシップ プロバイダーと照合する。</span><span class="sxs-lookup"><span data-stu-id="958d1-108">The server can validate the client credentials against the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
- <span data-ttu-id="958d1-109">サーバーがそのサーバーの X.509 証明書を使用して認証される。</span><span class="sxs-lookup"><span data-stu-id="958d1-109">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
- <span data-ttu-id="958d1-110">サーバーが [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ロール プロバイダーを使用して、認証されたクライアントをロールにマップする。</span><span class="sxs-lookup"><span data-stu-id="958d1-110">The server can map the authenticated client to a role by using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider.</span></span>  
  
- <span data-ttu-id="958d1-111">サーバーが `PrincipalPermissionAttribute` を使用して、サービスによって公開される特定メソッドへのアクセスを制御する。</span><span class="sxs-lookup"><span data-stu-id="958d1-111">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="958d1-112">メンバーシップとロール プロバイダーは、SQL Server によってサポートされるストアを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-112">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="958d1-113">接続文字列と各種オプションは、サービス構成ファイルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-113">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="958d1-114">メンバーシップ プロバイダーの名前は `SqlMembershipProvider` と指定され、ロール プロバイダーの名前は `SqlRoleProvider` と指定されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-114">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"   
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add   
        name="SqlMembershipProvider"   
        type="System.Web.Security.SqlMembershipProvider"   
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"   
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="958d1-115">サービスは、そのサービスとの通信に使用する単一エンドポイントを公開します。エンドポイントは Web.config 構成ファイルで定義します。</span><span class="sxs-lookup"><span data-stu-id="958d1-115">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="958d1-116">エンドポイントは、アドレス、バインディング、およびコントラクトがそれぞれ 1 つずつで構成されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="958d1-117">バインディングの構成には、標準の `wsHttpBinding` が使用されます。既定では、Windows 認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-117">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="958d1-118">このサンプルは、標準の `wsHttpBinding` を設定してユーザー名認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="958d1-118">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="958d1-119">この動作により、サービス認証でサーバー証明書が使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-119">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="958d1-120">サーバー証明書が同じ値を含める必要があります、`SubjectName`として、`findValue`属性、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)構成要素。</span><span class="sxs-lookup"><span data-stu-id="958d1-120">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="958d1-121">さらに、メンバーシップとロール プロバイダーで定義されている名前を指定することにより、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] メンバーシップ プロバイダーによってユーザー名とパスワードの組み合わせによる認証が実行され、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ロール プロバイダーによってロール マップが実行されることが、この動作によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-121">In addition the behavior specifies that authentication of username-password pairs is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider and role mapping is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider by specifying the names defined for the two providers.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"   
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"   
                              storeName ="My"   
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="958d1-122">サンプルを実行するときに、クライアントはの 3 つの異なるユーザー アカウント、さまざまなサービス操作を呼び出します。Alice、Bob、および Charlie します。</span><span class="sxs-lookup"><span data-stu-id="958d1-122">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="958d1-123">操作要求と応答は、クライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-123">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="958d1-124">ユーザー "Alice" として行われた 4 つの呼び出しはすべて正常に終了します。</span><span class="sxs-lookup"><span data-stu-id="958d1-124">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="958d1-125">ユーザー "Bob" には、Divide メソッドの呼び出しを試行したときにアクセス拒否エラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-125">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="958d1-126">ユーザー "Charlie" には、Multiply メソッドの呼び出しを試行したときにアクセス拒否エラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-126">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="958d1-127">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="958d1-127">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="958d1-128">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="958d1-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="958d1-129">ソリューションの c# または Visual Basic .NET 版をビルドする手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="958d1-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
2. <span data-ttu-id="958d1-130">構成したことを確認、 [ASP.NET アプリケーション サービス データベース](https://go.microsoft.com/fwlink/?LinkId=94997)します。</span><span class="sxs-lookup"><span data-stu-id="958d1-130">Ensure that you have configured the [ASP.NET Application Services Database](https://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958d1-131">SQL Server Express Edition を実行している場合、サーバー名は .\SQLEXPRESS になります。</span><span class="sxs-lookup"><span data-stu-id="958d1-131">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="958d1-132">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーション サービス データベースの構成および Web.config ファイルの接続文字列では、このサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958d1-132">This server should be used when configuring the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958d1-133">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ワーカー プロセス アカウントには、この手順で作成されるデータベースに対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="958d1-133">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="958d1-134">これを実行するには、sqlcmd ユーティリティまたは SQL Server Management Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="958d1-134">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3. <span data-ttu-id="958d1-135">サンプルを単一コンピューター構成で実行するか、複数コンピューター構成で実行するかに応じて、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="958d1-135">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="958d1-136">サンプルを同じコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="958d1-136">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="958d1-137">Makecert.exe が存在するフォルダーがパスに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="958d1-137">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="958d1-138">管理者特権で実行する Visual Studio 用開発者コマンド プロンプトでサンプルのインストール フォルダーから Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="958d1-138">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="958d1-139">これにより、サンプルの実行に必要なサービス証明書がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="958d1-139">This installs the service certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="958d1-140">Client.exe を \client\bin で起動します。</span><span class="sxs-lookup"><span data-stu-id="958d1-140">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="958d1-141">クライアント アクティビティがクライアントのコンソール アプリケーションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-141">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="958d1-142">クライアントとサービスが通信できるようにされていない場合[WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="958d1-142">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="958d1-143">サンプルを複数のコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="958d1-143">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="958d1-144">サービス コンピューターにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="958d1-144">Create a directory on the service computer.</span></span> <span data-ttu-id="958d1-145">インターネット インフォメーション サービス (IIS) 管理ツールを使用して、このディレクトリ用に servicemodelsamples という仮想アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="958d1-145">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="958d1-146">サービス プログラム ファイルを \inetpub\wwwroot\servicemodelsamples からサービス コンピューターの仮想ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-146">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="958d1-147">ファイルのコピー先が \bin サブディレクトリであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="958d1-147">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="958d1-148">Setup.bat、GetComputerName.vbs、Cleanup.bat の各ファイルもサービス コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-148">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="958d1-149">クライアント コンピューターにクライアント バイナリ用のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="958d1-149">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="958d1-150">クライアント プログラム ファイルを、クライアント コンピューターに作成したクライアント ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-150">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="958d1-151">Setup.bat、Cleanup.bat、ImportServiceCert.bat の各ファイルもクライアントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-151">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="958d1-152">サーバーで、管理者特権で Visual Studio の開発者コマンド プロンプトを開き、実行`setup.bat service`します。</span><span class="sxs-lookup"><span data-stu-id="958d1-152">On the server, open a Developer Command Prompt for Visual Studio with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="958d1-153">実行している`setup.bat`で、`service`引数が、コンピューターの完全修飾ドメイン名でサービス証明書を作成し、Service.cer というファイルに、サービス証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="958d1-153">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="958d1-154">新しい証明書名を反映するように Web.config を編集 (で、`findValue`属性、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md))、これは、コンピューターの完全修飾ドメイン名と同じです。</span><span class="sxs-lookup"><span data-stu-id="958d1-154">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="958d1-155">Service.cer ファイルを、サービス ディレクトリからクライアント コンピューターのクライアント ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-155">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="958d1-156">クライアント コンピューターの Client.exe.config ファイルで、エンドポイントのアドレス値をサービスの新しいアドレスに合わせます。</span><span class="sxs-lookup"><span data-stu-id="958d1-156">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="958d1-157">クライアントでは、管理者特権で Visual Studio の開発者コマンド プロンプトを開き、ImportServiceCert.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="958d1-157">On the client, open a Developer Command Prompt for Visual Studio with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="958d1-158">これにより、サービス証明書が Service.cer ファイルから CurrentUser - TrustedPeople ストアにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="958d1-158">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="958d1-159">クライアント コンピューターで、コマンド プロンプトから Client.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="958d1-159">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="958d1-160">クライアントとサービスが通信できるようにされていない場合[WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="958d1-160">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="958d1-161">サンプルの実行後にクリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="958d1-161">To clean up after the sample</span></span>  
  
- <span data-ttu-id="958d1-162">サンプルの実行が終わったら、サンプル フォルダーにある Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="958d1-162">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="958d1-163">このサンプルを複数のコンピューターで実行している場合、このスクリプトはサービス証明書をクライアントから削除しません。</span><span class="sxs-lookup"><span data-stu-id="958d1-163">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="958d1-164">コンピューター間で証明書を使用する Windows Communication Foundation (WCF) サンプルを実行すると、必ず、CurrentUser - TrustedPeople ストアにインストールされているサービス証明書をオフにします。</span><span class="sxs-lookup"><span data-stu-id="958d1-164">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="958d1-165">これを行うには、次のコマンドを使用します。`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 例:`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`します。</span><span class="sxs-lookup"><span data-stu-id="958d1-165">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="958d1-166">セットアップ バッチ ファイル</span><span class="sxs-lookup"><span data-stu-id="958d1-166">The Setup Batch File</span></span>  
 <span data-ttu-id="958d1-167">このサンプルに用意されている Setup.bat バッチ ファイルを使用すると、適切な証明書を使用してサーバーを構成し、サーバー証明書ベースのセキュリティを必要とする自己ホスト型アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="958d1-167">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="958d1-168">このバッチ ファイルは、複数のコンピューターを使用する場合またはホストなしの場合に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958d1-168">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="958d1-169">次に、バッチ ファイルのセクションのうち、該当する構成で実行するために変更が必要となる部分を示します。</span><span class="sxs-lookup"><span data-stu-id="958d1-169">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
- <span data-ttu-id="958d1-170">サーバー証明書の作成。</span><span class="sxs-lookup"><span data-stu-id="958d1-170">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="958d1-171">Setup.bat バッチ ファイルの次の行は、使用するサーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="958d1-171">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="958d1-172">%SERVER_NAME% 変数はサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="958d1-172">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="958d1-173">この変数を変更して、使用するサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="958d1-173">Change this variable to specify your own server name.</span></span> <span data-ttu-id="958d1-174">このバッチ ファイルでの既定は localhost です。</span><span class="sxs-lookup"><span data-stu-id="958d1-174">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="958d1-175">証明書は、LocalMachine ストアの場所の My (Personal) ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="958d1-175">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="958d1-176">クライアントの信頼された証明書ストアへのサーバー証明書のインストール。</span><span class="sxs-lookup"><span data-stu-id="958d1-176">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="958d1-177">Setup.bat バッチ ファイルの次の行は、サーバー証明書をクライアントの信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="958d1-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="958d1-178">この手順が必要なのは、Makecert.exe によって生成される証明書がクライアント システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="958d1-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="958d1-179">マイクロソフト発行の証明書など、クライアントの信頼されたルート証明書に基づいた証明書が既にある場合は、クライアント証明書ストアにサーバー証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="958d1-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
