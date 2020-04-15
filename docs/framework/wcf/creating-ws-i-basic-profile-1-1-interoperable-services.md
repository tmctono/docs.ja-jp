---
title: WS-I Basic Profile 1.1 の相互運用可能サービスの作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: fd7828cccb1a19a17e899525d863021d3670fbdd
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389761"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="00f61-102">WS-I Basic Profile 1.1 の相互運用可能サービスの作成</span><span class="sxs-lookup"><span data-stu-id="00f61-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="00f61-103">WCF サービス エンドポイントを構成して、Web サービス クライアントと相互運用可能ASP.NETするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00f61-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="00f61-104">サービス エンドポイントのバインディングの種類として <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> を使用する。</span><span class="sxs-lookup"><span data-stu-id="00f61-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="00f61-105">コールバック コントラクト機能とセッション コントラクト機能の使用、およびトランザクション動作のサービス エンドポイントでの使用をいずれも行わない。</span><span class="sxs-lookup"><span data-stu-id="00f61-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
<span data-ttu-id="00f61-106">必要に応じて、HTTPS およびトランスポート レベルのクライアント認証のサポートをバインディングで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="00f61-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
<span data-ttu-id="00f61-107"><xref:System.ServiceModel.BasicHttpBinding> クラスの次の機能を使用する場合、WS-I Basic Profile 1.1 の機能では十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="00f61-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="00f61-108"><xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> プロパティで制御される MTOM (Message Transmission Optimization Mechanism) メッセージ エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="00f61-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="00f61-109">MTOM を使用しない場合は、このプロパティを既定値 (<xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>) のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="00f61-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="00f61-110"><xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 値によって制御されるメッセージ セキュリティでは、WS-I Basic Security Profile 1.0 に準拠した WS-Security がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="00f61-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="00f61-111">WS-Security を使用しない場合は、このプロパティを既定値 (<xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>) のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="00f61-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
<span data-ttu-id="00f61-112">WCF サービスのメタデータをASP.NETで使用できるようにするには、Web サービスのクライアント生成ツールである[Web サービス記述言語ツール (Wsdl.exe)、Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29)[サービス探索ツール (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)、および Visual Studio の**Web 参照の追加**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="00f61-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the **Add Web Reference** feature in Visual Studio.</span></span> <span data-ttu-id="00f61-113">メタデータの公開を有効にします。</span><span class="sxs-lookup"><span data-stu-id="00f61-113">Enable metadata publication.</span></span> <span data-ttu-id="00f61-114">詳細については、「メタデータ[エンドポイントの公開](publishing-metadata-endpoints.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00f61-114">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f61-115">例</span><span class="sxs-lookup"><span data-stu-id="00f61-115">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="00f61-116">説明</span><span class="sxs-lookup"><span data-stu-id="00f61-116">Description</span></span>  
 <span data-ttu-id="00f61-117">次のコード例では、ASP.NET Web サービス クライアントと互換性のある WCF エンドポイントをコード内および構成ファイルに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="00f61-117">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="00f61-118">コード</span><span class="sxs-lookup"><span data-stu-id="00f61-118">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="00f61-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f61-119">See also</span></span>

- [<span data-ttu-id="00f61-120">ASP.NET Web サービスとの相互運用</span><span class="sxs-lookup"><span data-stu-id="00f61-120">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
