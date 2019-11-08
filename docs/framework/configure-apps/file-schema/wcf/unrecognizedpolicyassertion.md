---
title: <unrecognizedPolicyAssertion>
ms.date: 03/30/2017
ms.assetid: 043c3c8f-f263-4ac7-a1af-945d03413f0b
ms.openlocfilehash: 82a221c549efb68532a7a6f85446c5774d4a4d6a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732488"
---
# <a name="unrecognizedpolicyassertion"></a><span data-ttu-id="d4940-101">\<Un認識ポリシーアサーション ></span><span class="sxs-lookup"><span data-stu-id="d4940-101">\<unrecognizedPolicyAssertion></span></span>
<span data-ttu-id="d4940-102">ポリシー アサーションを指定するバインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d4940-102">Represents a binding element that specifies policy assertion.</span></span> <span data-ttu-id="d4940-103">この要素には属性がなく、空のスイッチとして表されます。</span><span class="sxs-lookup"><span data-stu-id="d4940-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="d4940-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4940-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4940-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="d4940-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d4940-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d4940-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d4940-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d4940-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="d4940-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="d4940-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d4940-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**un認識-Policyassertion >**</span><span class="sxs-lookup"><span data-stu-id="d4940-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<unrecognizedPolicyAssertion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4940-110">構文</span><span class="sxs-lookup"><span data-stu-id="d4940-110">Syntax</span></span>  
  
```xml  
<unrecognizedPolicyAssertion />
```  
  
## <a name="type"></a><span data-ttu-id="d4940-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="d4940-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4940-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4940-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d4940-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4940-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4940-114">属性</span><span class="sxs-lookup"><span data-stu-id="d4940-114">Attributes</span></span>  
 <span data-ttu-id="d4940-115">なし。</span><span class="sxs-lookup"><span data-stu-id="d4940-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4940-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d4940-116">Child Elements</span></span>  
 <span data-ttu-id="d4940-117">None</span><span class="sxs-lookup"><span data-stu-id="d4940-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4940-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d4940-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d4940-119">要素</span><span class="sxs-lookup"><span data-stu-id="d4940-119">Element</span></span>|<span data-ttu-id="d4940-120">説明</span><span class="sxs-lookup"><span data-stu-id="d4940-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4940-121">\<binding ></span><span class="sxs-lookup"><span data-stu-id="d4940-121">\<binding></span></span>](bindings.md)|<span data-ttu-id="d4940-122">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4940-122">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4940-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4940-123">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d4940-124">バインディング</span><span class="sxs-lookup"><span data-stu-id="d4940-124">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d4940-125">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="d4940-125">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d4940-126">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="d4940-126">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d4940-127">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d4940-127">\<customBinding></span></span>](custombinding.md)
