---
title: '方法: サービスのメッセージを検査および変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 87f9cf5040ffb757799c51d598d0755847c5bfd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767092"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="240c7-102">方法: サービスのメッセージを検査および変更する</span><span class="sxs-lookup"><span data-stu-id="240c7-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="240c7-103">検査または実装することで、Windows Communication Foundation (WCF) クライアントの受信または送信メッセージを変更することができます、<xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>をサービス ランタイムに挿入します。</span><span class="sxs-lookup"><span data-stu-id="240c7-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="240c7-104">詳細については、次を参照してください。[ディスパッチャーの拡張](../../../../docs/framework/wcf/extending/extending-dispatchers.md)します。</span><span class="sxs-lookup"><span data-stu-id="240c7-104">For more information, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span> <span data-ttu-id="240c7-105">サービスの同等の機能は、<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="240c7-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="240c7-106">メッセージを検査または変更するには</span><span class="sxs-lookup"><span data-stu-id="240c7-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="240c7-107"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="240c7-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="240c7-108">サービス メッセージ インスペクターを容易に挿入したいスコープに応じて、<xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>、<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>、または <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="240c7-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="240c7-109"><xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> で <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> メソッドを呼び出す前に、動作を挿入します。</span><span class="sxs-lookup"><span data-stu-id="240c7-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="240c7-110">詳細については、次を参照してください。[構成と、ランタイムの動作を拡張](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)します。</span><span class="sxs-lookup"><span data-stu-id="240c7-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="240c7-111">例</span><span class="sxs-lookup"><span data-stu-id="240c7-111">Example</span></span>  
 <span data-ttu-id="240c7-112">下のコード例では、次の項目を順番に示しています。</span><span class="sxs-lookup"><span data-stu-id="240c7-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="240c7-113">サービス インスペクターの実装</span><span class="sxs-lookup"><span data-stu-id="240c7-113">A service inspector implementation.</span></span>  
  
- <span data-ttu-id="240c7-114">インスペクターを挿入するサービス動作</span><span class="sxs-lookup"><span data-stu-id="240c7-114">A service behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="240c7-115">サービス アプリケーションに動作を読み込んで実行する構成ファイル</span><span class="sxs-lookup"><span data-stu-id="240c7-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="240c7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="240c7-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="240c7-117">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="240c7-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
