---
title: メッセージ資格情報付き WS トランスポート
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 54bd025db4da8ed1d1484b11666a37c2c14a6023
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949631"
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="cc601-102">メッセージ資格情報付き WS トランスポート</span><span class="sxs-lookup"><span data-stu-id="cc601-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="cc601-103">このサンプルでは、メッセージに含まれるクライアント資格情報と組み合わせて SSL トランスポート セキュリティを使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="cc601-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="cc601-104">このサンプルでは、`wsHttpBinding` バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc601-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="cc601-105">既定で、`wsHttpBinding` バインディングは HTTP 通信を実現します。</span><span class="sxs-lookup"><span data-stu-id="cc601-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="cc601-106">トランスポート セキュリティ用に構成すると、バインディングは HTTPS 通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cc601-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="cc601-107">HTTPS により、通信回線を介して送信されるメッセージについての機密性および整合性の保護が実現します。</span><span class="sxs-lookup"><span data-stu-id="cc601-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="cc601-108">ただし、サービスに対するクライアントの認証に使用できる一連の認証機構は、HTTPS トランスポートのサポート範囲に限定されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="cc601-109">Windows Communication Foundation (WCF) の提供、`TransportWithMessageCredential`セキュリティ モードは、この制限を克服するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="cc601-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="cc601-110">このセキュリティ モードが構成されると、送信メッセージの機密性および整合性を実現してサービス認証を実行する、トランスポート セキュリティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="cc601-111">ただし、クライアント認証は、クライアント資格情報をメッセージに直接配置することによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="cc601-112">これにより、トランスポート セキュリティ モードのパフォーマンスの利点を維持しながら、クライアント認証のメッセージ セキュリティ モードでサポートされている資格情報の種類を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cc601-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="cc601-113">このサンプルでは、サービスに対するクライアントの認証に `UserName` 資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="cc601-114">このサンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)電卓サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="cc601-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="cc601-115">`wsHttpBinding` バインディングは、クライアントとサービスのアプリケーション構成ファイルに指定され、構成されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc601-116">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc601-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cc601-117">プログラム コード サンプルではのとほぼ同じ、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)サービス。</span><span class="sxs-lookup"><span data-stu-id="cc601-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="cc601-118">`GetCallerIdentity` サービス コントラクトによって追加された操作が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="cc601-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="cc601-119">この操作は、呼び出し元の ID の名前を呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="cc601-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="cc601-120">このサンプルをビルドして実行する前に、証明書を作成し、Web サーバー証明書ウィザードを使用してあらかじめ割り当てておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc601-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="cc601-121">次に示すクライアント用構成の例のように、構成ファイル設定でエンドポイントとバインディングを定義すると、`TransportWithMessageCredential` セキュリティ モードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="cc601-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="cc601-122">アドレス指定では https:// スキームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="cc601-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="cc601-123">このバインド構成により、セキュリティ モードが `TransportWithMessageCredential` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="cc601-124">同じセキュリティ モードが、サービスの Web.config ファイルで指定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc601-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="cc601-125">Https にアクセスしようとするときにこのサンプルで使用される証明書は Makecert.exe で作成されたテスト証明書であるためセキュリティの警告が表示されます。 など、対処`https://localhost/servicemodelsamples/service.svc`、お使いのブラウザーから。</span><span class="sxs-lookup"><span data-stu-id="cc601-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as  `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span> <span data-ttu-id="cc601-126">インプレース テスト証明書を使用する WCF クライアントを許可するには、クライアントのセキュリティの警告を非表示に追加のコードが追加されました。</span><span class="sxs-lookup"><span data-stu-id="cc601-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="cc601-127">そのためのコードとそれに必要なクラスは、本運用の証明書を使用するときには不要です。</span><span class="sxs-lookup"><span data-stu-id="cc601-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="cc601-128">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc601-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="cc601-129">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cc601-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cc601-130">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="cc601-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cc601-131">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc601-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cc601-132">実行したことを確認、[インターネット インフォメーション サービス (IIS) サーバー証明書のインストール手順](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc601-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3. <span data-ttu-id="cc601-133">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cc601-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="cc601-134">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc601-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
