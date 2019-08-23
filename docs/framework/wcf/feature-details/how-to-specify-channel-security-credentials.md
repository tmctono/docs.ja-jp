---
title: '方法: チャネルのセキュリティ資格情報を指定する'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 3d6131a7488d9932118a988095791dd06fd46c49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933458"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="19d95-102">方法: チャネルのセキュリティ資格情報を指定する</span><span class="sxs-lookup"><span data-stu-id="19d95-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="19d95-103">Windows Communication Foundation (WCF) サービスモニカーを使用すると、COM アプリケーションから WCF サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19d95-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="19d95-104">ほとんどの WCF サービスでは、クライアントが認証と承認のための資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d95-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="19d95-105">Wcf クライアントから WCF サービスを呼び出すときに、これらの資格情報をマネージコードまたはアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="19d95-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="19d95-106">COM アプリケーションから WCF サービスを呼び出す場合は、インターフェイスを使用<xref:System.ServiceModel.ComIntegration.IChannelCredentials>して資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="19d95-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="19d95-107">ここでは、<xref:System.ServiceModel.ComIntegration.IChannelCredentials> インターフェイスを使用して資格情報を指定するさまざまな方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="19d95-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19d95-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> は IDispatch ベースのインターフェイスです。Visual Studio 環境で IntelliSense 機能を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="19d95-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="19d95-109">この記事では、[メッセージセキュリティのサンプル](../../../../docs/framework/wcf/samples/message-security-sample.md)で定義されている WCF サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="19d95-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="19d95-110">クライアント証明書を指定するには</span><span class="sxs-lookup"><span data-stu-id="19d95-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="19d95-111">メッセージ セキュリティのディレクトリの Setup.bat ファイルを実行し、必要なテスト証明書を作成してインストールします。</span><span class="sxs-lookup"><span data-stu-id="19d95-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="19d95-112">メッセージ セキュリティのプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="19d95-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="19d95-113">をインターフェイス定義に追加`[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]`します。 `ICalculator`</span><span class="sxs-lookup"><span data-stu-id="19d95-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="19d95-114">サービス`bindingNamespace="http://Microsoft.ServiceModel.Samples"`の app.config のエンドポイントタグにを追加します。</span><span class="sxs-lookup"><span data-stu-id="19d95-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="19d95-115">メッセージ セキュリティ サンプルをビルドし、Service.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="19d95-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="19d95-116">Internet Explorer を使用して、サービスの URI を http://localhost:8000/ServiceModelSamples/Service) 参照します (サービスが動作していることを確認します)。</span><span class="sxs-lookup"><span data-stu-id="19d95-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="19d95-117">Visual Basic 6.0 を開き、新しい標準 .exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19d95-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="19d95-118">フォームにボタンを追加し、追加したボタンをダブルクリックして次のコードをクリック ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d95-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. <span data-ttu-id="19d95-119">Visual Basic アプリケーションを実行し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="19d95-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="19d95-120">Visual Basic アプリケーションに Add(3,4) の結果を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d95-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="19d95-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> または <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> を <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> の代わりに使用して、クライアント証明書を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="19d95-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> <span data-ttu-id="19d95-122">この呼び出しを機能させるには、クライアントが実行されているコンピューターでクライアント証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d95-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19d95-123">モニカーの形式が正しくないか、`GetObject` を呼び出せない場合は、"構文が無効です" というメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="19d95-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="19d95-124">このエラーが発生した場合は、使用しているモニカーが正しく、サービスが使用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="19d95-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="19d95-125">ユーザー名とパスワードを指定するには</span><span class="sxs-lookup"><span data-stu-id="19d95-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="19d95-126">`wsHttpBinding` を使用するよう App.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="19d95-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="19d95-127">これは、ユーザー名とパスワードの検証に必要です。</span><span class="sxs-lookup"><span data-stu-id="19d95-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="19d95-128">`clientCredentialType` を UserName に設定します。</span><span class="sxs-lookup"><span data-stu-id="19d95-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="19d95-129">Visual Basic 6.0 を開き、新しい標準 .exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19d95-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="19d95-130">フォームにボタンを追加し、追加したボタンをダブルクリックして次のコードをクリック ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d95-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="19d95-131">Visual Basic アプリケーションを実行し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="19d95-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="19d95-132">Visual Basic アプリケーションに Add(3,4) の結果を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d95-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="19d95-133">この例のサービス モニカーに指定されたバインディングは、WSHttpBinding_ICalculator に変更されました。</span><span class="sxs-lookup"><span data-stu-id="19d95-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="19d95-134">また、<xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> の呼び出しにも有効なユーザー名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d95-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="19d95-135">Windows 資格情報を指定するには</span><span class="sxs-lookup"><span data-stu-id="19d95-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="19d95-136">サービスの App.config ファイルで、`clientCredentialType` を Windows に設定します。</span><span class="sxs-lookup"><span data-stu-id="19d95-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="19d95-137">Visual Basic 6.0 を開き、新しい標準 .exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19d95-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="19d95-138">フォームにボタンを追加し、追加したボタンをダブルクリックして次のコードをクリック ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d95-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="19d95-139">Visual Basic アプリケーションを実行し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="19d95-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="19d95-140">Visual Basic アプリケーションに Add(3,4) の結果を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d95-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="19d95-141">"ドメイン"、"ユーザー ID"、"パスワード" を有効な値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d95-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="19d95-142">発行トークンを指定するには</span><span class="sxs-lookup"><span data-stu-id="19d95-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="19d95-143">発行トークンは、フェデレーション セキュリティを使用するアプリケーションのみが使用します。</span><span class="sxs-lookup"><span data-stu-id="19d95-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="19d95-144">フェデレーションセキュリティの詳細については、「[フェデレーションと発行済みトークン](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)および[フェデレーションのサンプル](../../../../docs/framework/wcf/samples/federation-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d95-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="19d95-145"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> メソッドを呼び出す方法を次の Visual Basic コード例に示します。</span><span class="sxs-lookup"><span data-stu-id="19d95-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="19d95-146">このメソッドのパラメーターの詳細については、<xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d95-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d95-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="19d95-147">See also</span></span>

- [<span data-ttu-id="19d95-148">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="19d95-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="19d95-149">方法: フェデレーションサービスで資格情報を構成する</span><span class="sxs-lookup"><span data-stu-id="19d95-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="19d95-150">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="19d95-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="19d95-151">メッセージのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="19d95-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="19d95-152">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="19d95-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
