---
title: '方法: ユーザー名とパスワードで認証する'
description: WCF サービスで、Windows ドメインのユーザー名とパスワードをサンプルコードと共に使用して、クライアントを認証できるようにする方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 1f938f8041b2577b3705266948f29b42f23a6fd7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247248"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="a47fe-103">方法: ユーザー名とパスワードで認証する</span><span class="sxs-lookup"><span data-stu-id="a47fe-103">How to: Authenticate with a User Name and Password</span></span>

<span data-ttu-id="a47fe-104">このトピックでは、Windows Communication Foundation (WCF) サービスを有効にして、Windows ドメインのユーザー名とパスワードを使用してクライアントを認証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-104">This topic demonstrates how to enable a Windows Communication Foundation (WCF) service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="a47fe-105">自己ホスト型 WCF サービスが稼働していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a47fe-105">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="a47fe-106">基本的な自己ホスト型 WCF サービスを作成する例については、[はじめにチュートリアル](../getting-started-tutorial.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47fe-106">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="a47fe-107">このトピックでは、サービスがコードで構成されているものとします。</span><span class="sxs-lookup"><span data-stu-id="a47fe-107">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="a47fe-108">構成ファイルを使用して同様のサービスを構成する例については、「[メッセージセキュリティユーザー名](../samples/message-security-user-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47fe-108">If you would like to see an example of configuring a similar service using a configuration file, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>

<span data-ttu-id="a47fe-109">Windows ドメイン ユーザー名とパスワードを使用してクライアントを認証するようにサービスを構成するには、<xref:System.ServiceModel.WSHttpBinding> を使用し、その `Security.Mode` プロパティを `Message` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-109">To configure a service to authenticate its clients using Windows Domain username and passwords use the <xref:System.ServiceModel.WSHttpBinding> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="a47fe-110">また、ユーザー名とパスワードをクライアントからサービスに送信するときに X.509 証明書を指定する必要があります。この証明書は、ユーザー名とパスワードの暗号化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a47fe-110">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>

<span data-ttu-id="a47fe-111">クライアント側では、ユーザーにユーザー名とパスワードの入力を求め、WCF クライアント プロキシでユーザーの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47fe-111">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="a47fe-112">Windows ドメインのユーザー名とパスワードを使用して認証するように WCF サービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="a47fe-112">To configure a WCF service to authenticate using Windows domain username and password</span></span>

1. <span data-ttu-id="a47fe-113">次のコードに示すように、<xref:System.ServiceModel.WSHttpBinding> のインスタンスを作成し、バインディングのセキュリティ モードを <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType> に設定した後、バインディングの `ClientCredentialType` を <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> に設定し、構成されたバインディングを使用するサービス エンドポイントをサービス ホストに追加します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-113">Create an instance of the <xref:System.ServiceModel.WSHttpBinding>, set the security mode of the binding to <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, set the `ClientCredentialType` of the binding to <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType>, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. <span data-ttu-id="a47fe-114">ネットワーク経由で送信されるユーザー名とパスワードの情報を暗号化するために使用するサーバー証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-114">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="a47fe-115">次のコードは、上記のコードの直後に追加します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-115">This code should immediately follow the code above.</span></span> <span data-ttu-id="a47fe-116">次の例では、[メッセージセキュリティユーザー名](../samples/message-security-user-name.md)のサンプルから、setup.bat ファイルによって作成された証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-116">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../samples/message-security-user-name.md) sample:</span></span>

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    <span data-ttu-id="a47fe-117">独自の証明書を使用する場合は、その証明書を参照するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-117">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="a47fe-118">証明書の作成と使用の詳細については、「[証明書の](working-with-certificates.md)使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47fe-118">For more information about creating and using certificates see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="a47fe-119">証明書がローカル コンピューターの信頼されたユーザー証明書ストア内に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-119">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="a47fe-120">これを行うには、mmc.exe を実行し、[**ファイル**] メニューの [スナップインの**追加と削除**] メニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-120">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="a47fe-121">[スナップインの**追加と削除**] ダイアログで、[**証明書] スナップ**インを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a47fe-121">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="a47fe-122">[証明書スナップイン] ダイアログで、[**コンピューターアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-122">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="a47fe-123">既定では、「メッセージ セキュリティ ユーザー名」のサンプルから生成された証明書は個人/証明書フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a47fe-123">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="a47fe-124">これは、MMC ウィンドウの [発行先] 列の下に "localhost" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="a47fe-124">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="a47fe-125">証明書を [**信頼さ**れた People] フォルダーにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="a47fe-125">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="a47fe-126">これにより、WCF は、認証の実行時に、証明書を信頼された証明書として処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a47fe-126">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>

## <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="a47fe-127">ユーザー名とパスワードを渡すサービスを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="a47fe-127">To call the service passing username and password</span></span>

1. <span data-ttu-id="a47fe-128">クライアント アプリケーションは、ユーザー名とパスワードの入力をユーザーに求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47fe-128">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="a47fe-129">次のコードでは、ユーザーにユーザー名とパスワードの入力を求めています。</span><span class="sxs-lookup"><span data-stu-id="a47fe-129">The following code asks the user for username and password:</span></span>

    > [!WARNING]
    > <span data-ttu-id="a47fe-130">このコードは、入力中のパスワードが表示されるため、運用環境では使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a47fe-130">This code should not be used in production as the password is displayed while being entered.</span></span>

    ```csharp
    public static void GetPassword(out string username, out string password)
    {
        Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");
        Console.WriteLine("   Enter username:");
        username = Console.ReadLine();
        Console.WriteLine("   Enter password:");
        password = Console.ReadLine();
    }
    ```

2. <span data-ttu-id="a47fe-131">次のコードに示すように、クライアントの資格情報を指定して、クライアントプロキシのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a47fe-131">Create an instance of the client proxy specifying the client's credentials as shown in the following code:</span></span>

    ```csharp
    string username;
    string password;

    // Instantiate the proxy.
    var proxy = new Service1Client();

    // Prompt the user for username & password.
    GetPassword(out username, out password);

    // Set the user's credentials on the proxy.
    proxy.ClientCredentials.UserName.UserName = username;
    proxy.ClientCredentials.UserName.Password = password;

    // Treat the test certificate as trusted.
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;
    // Call the service operation using the proxy
    ```

## <a name="see-also"></a><span data-ttu-id="a47fe-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a47fe-132">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [<span data-ttu-id="a47fe-133">基本認証でのトランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="a47fe-133">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)
- [<span data-ttu-id="a47fe-134">分散アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a47fe-134">Distributed Application Security</span></span>](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
