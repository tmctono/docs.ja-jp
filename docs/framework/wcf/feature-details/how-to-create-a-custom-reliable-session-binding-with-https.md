---
title: '方法 : カスタムの信頼できるセッションによる HTTPS を使用したバインディングを作成する'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 26466a97ae44e6852c189d0b72bdba1b93d86141
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141735"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="2772f-102">方法 : カスタムの信頼できるセッションによる HTTPS を使用したバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="2772f-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="2772f-103">ここでは、信頼できるセッションを使用した SSL (Secure Sockets Layer) トランスポート セキュリティの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2772f-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="2772f-104">HTTPS 上で信頼できるセッションを使用するには、信頼できるセッションと HTTPS トランスポートを使用するカスタム バインドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2772f-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="2772f-105">信頼できるセッションは、コードを使用するか、構成ファイルで宣言によって、強制的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="2772f-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="2772f-106">この手順では、クライアントとサービスの構成ファイルを使用して、信頼できるセッションと[ **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)要素を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2772f-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="2772f-107">この手順の重要な部分は、 **\<エンドポイント >** 構成要素に、`reliableSessionOverHttps`という名前のカスタムバインド構成を参照する `bindingConfiguration` 属性が含まれていることです。</span><span class="sxs-lookup"><span data-stu-id="2772f-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="2772f-108">[ **\<binding >** ](../../configure-apps/file-schema/wcf/bindings.md) configuration 要素は、この名前を参照して、信頼できるセッションと HTTPS トランスポートを使用することを指定します。これは **\<reliableSession >** および **\<httpsTransport >** 要素を含めることによって行います。</span><span class="sxs-lookup"><span data-stu-id="2772f-108">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="2772f-109">この例のソースコピーについては、「HTTPS を使用した[カスタムバインディングの信頼できるセッション](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2772f-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="2772f-110">HTTPS で信頼できるセッションを使用するための CustomBinding でサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="2772f-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="2772f-111">サービスの種類にサービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="2772f-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="2772f-112">サービス クラスにサービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="2772f-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="2772f-113">サービスの実装内では、アドレスまたはバインド情報が指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2772f-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="2772f-114">構成ファイルからアドレスやバインド情報を取得するためのコードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2772f-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="2772f-115">*Web.config ファイルを*作成し、信頼できるセッションと HTTPS トランスポートを使用する `reliableSessionOverHttps` という名前のカスタムバインディングを使用して、`CalculatorService` のエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2772f-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="2772f-116">次の行を含む .svc ファイルを作成*し*ます。</span><span class="sxs-lookup"><span data-stu-id="2772f-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="2772f-117">サービスの *.svc*ファイルをインターネットインフォメーションサービス (IIS) 仮想ディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="2772f-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="2772f-118">HTTPS で信頼できるセッションを使用するようにクライアントを構成する (CustomBinding)</span><span class="sxs-lookup"><span data-stu-id="2772f-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="2772f-119">コマンドラインから[ServiceModel メタデータユーティリティツール (*svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、サービスメタデータからコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="2772f-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="2772f-120">生成されるクライアントには、クライアント実装が満たす必要のあるサービスコントラクトを定義する `ICalculator` インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2772f-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="2772f-121">生成されたクライアント アプリケーションは `ClientCalculator` も実装します。</span><span class="sxs-lookup"><span data-stu-id="2772f-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="2772f-122">サービスの実装内でアドレスとバインディング情報が指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2772f-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="2772f-123">構成ファイルからアドレスおよびバインド情報を取得するコードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2772f-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="2772f-124">HTTPS トランスポートと信頼できるセッションを使用するように、`reliableSessionOverHttps` という名前のカスタムバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="2772f-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="2772f-125">アプリケーションで `ClientCalculator` のインスタンスを作成し、サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2772f-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="2772f-126">クライアントをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="2772f-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="2772f-127">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="2772f-127">.NET Framework security</span></span>

<span data-ttu-id="2772f-128">このサンプルで使用される証明書は、 *Makecert*で作成されたテスト証明書であるため、ブラウザーから HTTPS アドレス (`https://localhost/servicemodelsamples/service.svc`など) にアクセスしようとすると、セキュリティの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2772f-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="2772f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="2772f-129">See also</span></span>

- [<span data-ttu-id="2772f-130">信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="2772f-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
