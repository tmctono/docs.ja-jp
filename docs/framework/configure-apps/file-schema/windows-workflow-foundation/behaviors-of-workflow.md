---
title: <behaviors>ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398874"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="f95e2-102">\<behaviors>ワークフローの</span><span class="sxs-lookup"><span data-stu-id="f95e2-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="f95e2-103">この要素には、 **Servicebehaviors**コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f95e2-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="f95e2-104">コレクション内の各要素は、ワークフロー サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="f95e2-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="f95e2-105">各動作要素は、一意の**name**属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="f95e2-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="f95e2-106">構文</span><span class="sxs-lookup"><span data-stu-id="f95e2-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f95e2-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f95e2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f95e2-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f95e2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f95e2-109">属性</span><span class="sxs-lookup"><span data-stu-id="f95e2-109">Attributes</span></span>  
 <span data-ttu-id="f95e2-110">なし</span><span class="sxs-lookup"><span data-stu-id="f95e2-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f95e2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f95e2-111">Child Elements</span></span>  
  
|<span data-ttu-id="f95e2-112">要素</span><span class="sxs-lookup"><span data-stu-id="f95e2-112">Element</span></span>|<span data-ttu-id="f95e2-113">説明</span><span class="sxs-lookup"><span data-stu-id="f95e2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="f95e2-114">この構成セクションは、特定のワークフロー サービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="f95e2-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f95e2-115">親要素</span><span class="sxs-lookup"><span data-stu-id="f95e2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f95e2-116">要素</span><span class="sxs-lookup"><span data-stu-id="f95e2-116">Element</span></span>|<span data-ttu-id="f95e2-117">説明</span><span class="sxs-lookup"><span data-stu-id="f95e2-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="f95e2-118">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="f95e2-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f95e2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f95e2-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="f95e2-120">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="f95e2-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
