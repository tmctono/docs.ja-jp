---
title: '方法 : 信頼されたセッション内のメッセージを変換する'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 58a392fc6295e82f41e08c80a3343b4059afad7e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141680"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="fa2b2-102">方法 : 信頼されたセッション内のメッセージを変換する</span><span class="sxs-lookup"><span data-stu-id="fa2b2-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="fa2b2-103">このトピックでは、信頼できるセッションを有効にするために必要な手順について説明します。ここでは、信頼できるセッションを (既定ではなく) オプションでサポートするシステム指定のバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="fa2b2-104">信頼できるセッションは、コードまたは構成ファイルで宣言によって強制的に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="fa2b2-105">この手順では、クライアントとサービスの構成ファイルを使用して、信頼できるセッションを有効にし、メッセージが送信された順序と同じ順序で到着することを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="fa2b2-106">この手順の重要な部分は、エンドポイント構成要素に、`Binding1`という名前のバインディング構成を参照する `bindingConfiguration` 属性が含まれていることです。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="fa2b2-107">[ **\<binding >** ](../../configure-apps/file-schema/wcf/bindings.md) configuration 要素は、 [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100))要素の `enabled` 属性を `true`に設定することによって、この名前を参照して信頼できるセッションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-107">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) element to `true`.</span></span> <span data-ttu-id="fa2b2-108">信頼できるセッションで順序付き配信の保証を指定するには、`ordered` 属性を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="fa2b2-109">この例のソースコピーについては、「 [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fa2b2-110">信頼できるセッションを使用するようにサービスを WSHttpBinding で構成する</span><span class="sxs-lookup"><span data-stu-id="fa2b2-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="fa2b2-111">サービスの種類にサービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="fa2b2-112">サービス クラスにサービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="fa2b2-113">サービスの実装内では、アドレスまたはバインド情報が指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fa2b2-114">構成ファイルからアドレスやバインド情報を取得するためのコードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="fa2b2-115">*Web.config ファイルを*作成して、信頼できるセッションを有効にし、必要なメッセージを順次配信する <xref:System.ServiceModel.WSHttpBinding> を使用する `CalculatorService` のエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="fa2b2-116">次の行を含む .svc ファイルを作成*し*ます。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="fa2b2-117">サービスの *.svc*ファイルをインターネットインフォメーションサービス (IIS) 仮想ディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fa2b2-118">信頼できるセッションを使用するようにクライアントを WSHttpBinding で構成する</span><span class="sxs-lookup"><span data-stu-id="fa2b2-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="fa2b2-119">コマンドラインから[ServiceModel メタデータユーティリティツール (*svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、サービスメタデータからコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="fa2b2-120">生成されたクライアントには、クライアント実装が満たす必要のあるサービスコントラクトを定義する `ICalculator` インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="fa2b2-121">生成されたクライアント アプリケーションは `ClientCalculator` も実装します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="fa2b2-122">サービスの実装内でアドレスおよびバインド情報が指定されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="fa2b2-123">構成ファイルからアドレスやバインド情報を取得するためのコードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="fa2b2-124">*Svcutil.exe*は、<xref:System.ServiceModel.WSHttpBinding> クラスを使用するクライアントの構成も生成します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="fa2b2-125">Visual Studio を使用*する場合は*、構成ファイルに app.config という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="fa2b2-126">アプリケーションで `ClientCalculator` のインスタンスを作成し、サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="fa2b2-127">クライアントをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="fa2b2-128">例</span><span class="sxs-lookup"><span data-stu-id="fa2b2-128">Example</span></span>

<span data-ttu-id="fa2b2-129">システム指定のバインディングの中には、信頼できるセッションを既定でサポートするものがあります。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="fa2b2-130">次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="fa2b2-131">信頼できるセッションをサポートするカスタムバインディングを作成する方法の例については、「[方法: HTTPS を使用してカスタムの信頼できるセッションのバインディングを作成](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2b2-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa2b2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa2b2-132">See also</span></span>

- [<span data-ttu-id="fa2b2-133">信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="fa2b2-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
