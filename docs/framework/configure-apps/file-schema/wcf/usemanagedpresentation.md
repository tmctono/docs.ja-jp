---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: eedf0ce6cf75b8fb56daf98f2005e66162ce10d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155656"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="20b92-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="20b92-101">\<useManagedPresentation></span></span>
<span data-ttu-id="20b92-102">WS-Trust の CardSpace プロファイルをサポートする CardSpace セキュリティ トークン サービスとの通信に使用するバインド要素。</span><span class="sxs-lookup"><span data-stu-id="20b92-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="20b92-103">この要素には属性がなく、空のスイッチとして表されます。</span><span class="sxs-lookup"><span data-stu-id="20b92-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="20b92-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20b92-104">\<system.serviceModel></span></span>  
<span data-ttu-id="20b92-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="20b92-105">\<bindings></span></span>  
<span data-ttu-id="20b92-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="20b92-106">\<customBinding></span></span>  
<span data-ttu-id="20b92-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="20b92-107">\<binding></span></span>  
<span data-ttu-id="20b92-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="20b92-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b92-109">構文</span><span class="sxs-lookup"><span data-stu-id="20b92-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20b92-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="20b92-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20b92-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20b92-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20b92-112">属性</span><span class="sxs-lookup"><span data-stu-id="20b92-112">Attributes</span></span>  
 <span data-ttu-id="20b92-113">なし。</span><span class="sxs-lookup"><span data-stu-id="20b92-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20b92-114">子要素</span><span class="sxs-lookup"><span data-stu-id="20b92-114">Child Elements</span></span>  
 <span data-ttu-id="20b92-115">なし</span><span class="sxs-lookup"><span data-stu-id="20b92-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20b92-116">親要素</span><span class="sxs-lookup"><span data-stu-id="20b92-116">Parent Elements</span></span>  
  
|<span data-ttu-id="20b92-117">要素</span><span class="sxs-lookup"><span data-stu-id="20b92-117">Element</span></span>|<span data-ttu-id="20b92-118">説明</span><span class="sxs-lookup"><span data-stu-id="20b92-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20b92-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="20b92-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="20b92-120">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="20b92-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20b92-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="20b92-121">Remarks</span></span>  
 <span data-ttu-id="20b92-122">この要素は、WS-Trust の CardSpace プロファイルをサポートするという事実をポリシーで明示するために、ID プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="20b92-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="20b92-123">このようなポリシー アサーションを公開する ID プロバイダーは、その CardSpace プロファイルに基づくトークンを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="20b92-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b92-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="20b92-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="20b92-125">バインディング</span><span class="sxs-lookup"><span data-stu-id="20b92-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="20b92-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="20b92-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="20b92-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="20b92-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="20b92-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="20b92-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
