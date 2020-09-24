---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 86a6f975b05133d5f9f21fcfb82ef4c23d2ffaba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148813"
---
# \<useManagedPresentation>

<span data-ttu-id="8c8b8-101">WS-Trust の CardSpace プロファイルをサポートする CardSpace セキュリティ トークン サービスとの通信に使用するバインド要素。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="8c8b8-102">この要素には属性がなく、空のスイッチとして表されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="8c8b8-103">構文</span><span class="sxs-lookup"><span data-stu-id="8c8b8-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c8b8-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c8b8-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8c8b8-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c8b8-106">属性</span><span class="sxs-lookup"><span data-stu-id="8c8b8-106">Attributes</span></span>  

 <span data-ttu-id="8c8b8-107">なし。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c8b8-108">子要素</span><span class="sxs-lookup"><span data-stu-id="8c8b8-108">Child Elements</span></span>  

 <span data-ttu-id="8c8b8-109">None</span><span class="sxs-lookup"><span data-stu-id="8c8b8-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c8b8-110">親要素</span><span class="sxs-lookup"><span data-stu-id="8c8b8-110">Parent Elements</span></span>  
  
|<span data-ttu-id="8c8b8-111">要素</span><span class="sxs-lookup"><span data-stu-id="8c8b8-111">Element</span></span>|<span data-ttu-id="8c8b8-112">説明</span><span class="sxs-lookup"><span data-stu-id="8c8b8-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8c8b8-113">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c8b8-114">解説</span><span class="sxs-lookup"><span data-stu-id="8c8b8-114">Remarks</span></span>  

 <span data-ttu-id="8c8b8-115">この要素は、WS-Trust の CardSpace プロファイルをサポートするという事実をポリシーで明示するために、ID プロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="8c8b8-116">このようなポリシー アサーションを公開する ID プロバイダーは、その CardSpace プロファイルに基づくトークンを発行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c8b8-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8b8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c8b8-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8c8b8-118">バインド</span><span class="sxs-lookup"><span data-stu-id="8c8b8-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8c8b8-119">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="8c8b8-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8c8b8-120">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="8c8b8-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
