---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738777"
---
# \<pnrpPeerResolver>
<span data-ttu-id="728f4-101">リゾルバーとして PNRP (Peer Name Resolution Protocol) リゾルバーを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="728f4-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="728f4-102">PNRP は既定のリゾルバーであるため、この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="728f4-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="728f4-103">構文</span><span class="sxs-lookup"><span data-stu-id="728f4-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="728f4-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="728f4-104">Attributes and Elements</span></span>  
 <span data-ttu-id="728f4-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="728f4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="728f4-106">属性</span><span class="sxs-lookup"><span data-stu-id="728f4-106">Attributes</span></span>  
  
|<span data-ttu-id="728f4-107">属性</span><span class="sxs-lookup"><span data-stu-id="728f4-107">Attribute</span></span>|<span data-ttu-id="728f4-108">説明</span><span class="sxs-lookup"><span data-stu-id="728f4-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="728f4-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="728f4-109">resolverType</span></span>|<span data-ttu-id="728f4-110">使用されるリゾルバーを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="728f4-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="728f4-111">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="728f4-111">This attribute is optional.</span></span> <span data-ttu-id="728f4-112">設定されていない場合、または空の文字列に設定されている場合は、PNRP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="728f4-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="728f4-113">子要素</span><span class="sxs-lookup"><span data-stu-id="728f4-113">Child Elements</span></span>  
 <span data-ttu-id="728f4-114">なし</span><span class="sxs-lookup"><span data-stu-id="728f4-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="728f4-115">親要素</span><span class="sxs-lookup"><span data-stu-id="728f4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="728f4-116">要素</span><span class="sxs-lookup"><span data-stu-id="728f4-116">Element</span></span>|<span data-ttu-id="728f4-117">Description</span><span class="sxs-lookup"><span data-stu-id="728f4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="728f4-118">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="728f4-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="728f4-119">例</span><span class="sxs-lookup"><span data-stu-id="728f4-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="728f4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="728f4-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="728f4-121">バインド</span><span class="sxs-lookup"><span data-stu-id="728f4-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="728f4-122">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="728f4-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="728f4-123">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="728f4-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="728f4-124">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="728f4-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
