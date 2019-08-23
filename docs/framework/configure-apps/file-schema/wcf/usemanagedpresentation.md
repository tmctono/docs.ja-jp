---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940612"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="2e400-101">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="2e400-101">\<useManagedPresentation></span></span>
<span data-ttu-id="2e400-102">WS-Trust の CardSpace プロファイルをサポートする CardSpace セキュリティ トークン サービスとの通信に使用するバインド要素。</span><span class="sxs-lookup"><span data-stu-id="2e400-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="2e400-103">この要素には属性がなく、空のスイッチとして表されます。</span><span class="sxs-lookup"><span data-stu-id="2e400-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="2e400-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2e400-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2e400-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2e400-105">\<bindings></span></span>  
<span data-ttu-id="2e400-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2e400-106">\<customBinding></span></span>  
<span data-ttu-id="2e400-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e400-107">\<binding></span></span>  
<span data-ttu-id="2e400-108">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="2e400-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e400-109">構文</span><span class="sxs-lookup"><span data-stu-id="2e400-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e400-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e400-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e400-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e400-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e400-112">属性</span><span class="sxs-lookup"><span data-stu-id="2e400-112">Attributes</span></span>  
 <span data-ttu-id="2e400-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2e400-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e400-114">子要素</span><span class="sxs-lookup"><span data-stu-id="2e400-114">Child Elements</span></span>  
 <span data-ttu-id="2e400-115">なし</span><span class="sxs-lookup"><span data-stu-id="2e400-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e400-116">親要素</span><span class="sxs-lookup"><span data-stu-id="2e400-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2e400-117">要素</span><span class="sxs-lookup"><span data-stu-id="2e400-117">Element</span></span>|<span data-ttu-id="2e400-118">説明</span><span class="sxs-lookup"><span data-stu-id="2e400-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e400-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e400-119">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2e400-120">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e400-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e400-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e400-121">Remarks</span></span>  
 <span data-ttu-id="2e400-122">この要素は、WS-Trust の CardSpace プロファイルをサポートするという事実をポリシーで明示するために、ID プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e400-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="2e400-123">このようなポリシー アサーションを公開する ID プロバイダーは、その CardSpace プロファイルに基づくトークンを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e400-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e400-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e400-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2e400-125">バインディング</span><span class="sxs-lookup"><span data-stu-id="2e400-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e400-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="2e400-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2e400-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="2e400-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2e400-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2e400-128">\<customBinding></span></span>](custombinding.md)
