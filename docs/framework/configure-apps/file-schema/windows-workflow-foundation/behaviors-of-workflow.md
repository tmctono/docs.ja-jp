---
title: <behaviors>ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398874"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="4fb46-102">\<ワークフローの動作 ></span><span class="sxs-lookup"><span data-stu-id="4fb46-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="4fb46-103">この要素には、 **Servicebehaviors**コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4fb46-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="4fb46-104">コレクション内の各要素は、ワークフロー サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fb46-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="4fb46-105">各動作要素は、一意の**name**属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="4fb46-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="4fb46-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4fb46-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4fb46-107">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4fb46-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4fb46-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<動作 >**</span><span class="sxs-lookup"><span data-stu-id="4fb46-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb46-109">構文</span><span class="sxs-lookup"><span data-stu-id="4fb46-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fb46-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4fb46-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4fb46-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fb46-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fb46-112">属性</span><span class="sxs-lookup"><span data-stu-id="4fb46-112">Attributes</span></span>  
 <span data-ttu-id="4fb46-113">なし</span><span class="sxs-lookup"><span data-stu-id="4fb46-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fb46-114">子要素</span><span class="sxs-lookup"><span data-stu-id="4fb46-114">Child Elements</span></span>  
  
|<span data-ttu-id="4fb46-115">要素</span><span class="sxs-lookup"><span data-stu-id="4fb46-115">Element</span></span>|<span data-ttu-id="4fb46-116">説明</span><span class="sxs-lookup"><span data-stu-id="4fb46-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fb46-117">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4fb46-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="4fb46-118">この構成セクションは、特定のワークフロー サービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="4fb46-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fb46-119">親要素</span><span class="sxs-lookup"><span data-stu-id="4fb46-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4fb46-120">要素</span><span class="sxs-lookup"><span data-stu-id="4fb46-120">Element</span></span>|<span data-ttu-id="4fb46-121">説明</span><span class="sxs-lookup"><span data-stu-id="4fb46-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fb46-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4fb46-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="4fb46-123">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="4fb46-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fb46-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fb46-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="4fb46-125">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="4fb46-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
