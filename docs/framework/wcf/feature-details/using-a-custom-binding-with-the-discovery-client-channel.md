---
title: カスタム バインドを探索クライアント チャネルと共に使用する
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 6fe9370bb22ca424774fc8cb4566e0802bc06697
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918620"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="3c21a-102">カスタム バインドを探索クライアント チャネルと共に使用する</span><span class="sxs-lookup"><span data-stu-id="3c21a-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="3c21a-103">カスタム バインドを <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> と共に使用する場合は、<xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> インスタンスを作成する <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c21a-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="3c21a-104">DiscoveryEndpointProvider の作成</span><span class="sxs-lookup"><span data-stu-id="3c21a-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="3c21a-105"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>作成を担当<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>オンデマンド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="3c21a-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="3c21a-106">探索エンドポイント プロバイダーを定義するには、<xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> からクラスを派生させ、<xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> メソッドをオーバーライドし、新しい探索エンドポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="3c21a-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="3c21a-107">次の例は、探索エンドポイント プロバイダーを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c21a-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel   
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 <span data-ttu-id="3c21a-108">探索エンドポイント プロバイダーを定義したら、次の例に示すように、カスタム バインドを作成し、その探索エンドポイント プロバイダーを参照する <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c21a-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="3c21a-109">探索クライアント チャネルの使用に関する詳細については、次を参照してください。[探索クライアント チャネルを使用して](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c21a-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c21a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c21a-110">See also</span></span>

- [<span data-ttu-id="3c21a-111">WCF Discovery の概要</span><span class="sxs-lookup"><span data-stu-id="3c21a-111">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="3c21a-112">探索クライアント チャネルの使用</span><span class="sxs-lookup"><span data-stu-id="3c21a-112">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
