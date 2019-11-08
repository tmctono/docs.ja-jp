---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735938"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="3cd44-101">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="3cd44-101">\<useManagedPresentation></span></span>
<span data-ttu-id="3cd44-102">WS-Trust の CardSpace プロファイルをサポートする CardSpace セキュリティ トークン サービスとの通信に使用するバインド要素。</span><span class="sxs-lookup"><span data-stu-id="3cd44-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="3cd44-103">この要素には属性がなく、空のスイッチとして表されます。</span><span class="sxs-lookup"><span data-stu-id="3cd44-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="3cd44-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cd44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cd44-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="3cd44-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3cd44-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3cd44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3cd44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cd44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="3cd44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="3cd44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3cd44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**useManagedPresentation >**</span><span class="sxs-lookup"><span data-stu-id="3cd44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cd44-110">構文</span><span class="sxs-lookup"><span data-stu-id="3cd44-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cd44-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3cd44-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3cd44-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cd44-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cd44-113">属性</span><span class="sxs-lookup"><span data-stu-id="3cd44-113">Attributes</span></span>  
 <span data-ttu-id="3cd44-114">なし。</span><span class="sxs-lookup"><span data-stu-id="3cd44-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cd44-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3cd44-115">Child Elements</span></span>  
 <span data-ttu-id="3cd44-116">None</span><span class="sxs-lookup"><span data-stu-id="3cd44-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cd44-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3cd44-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3cd44-118">要素</span><span class="sxs-lookup"><span data-stu-id="3cd44-118">Element</span></span>|<span data-ttu-id="3cd44-119">説明</span><span class="sxs-lookup"><span data-stu-id="3cd44-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cd44-120">\<binding ></span><span class="sxs-lookup"><span data-stu-id="3cd44-120">\<binding></span></span>](bindings.md)|<span data-ttu-id="3cd44-121">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cd44-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cd44-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cd44-122">Remarks</span></span>  
 <span data-ttu-id="3cd44-123">この要素は、WS-Trust の CardSpace プロファイルをサポートするという事実をポリシーで明示するために、ID プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cd44-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="3cd44-124">このようなポリシー アサーションを公開する ID プロバイダーは、その CardSpace プロファイルに基づくトークンを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cd44-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd44-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cd44-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3cd44-126">バインディング</span><span class="sxs-lookup"><span data-stu-id="3cd44-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3cd44-127">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="3cd44-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3cd44-128">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="3cd44-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3cd44-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3cd44-129">\<customBinding></span></span>](custombinding.md)
