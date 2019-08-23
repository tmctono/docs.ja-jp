---
title: <behaviors>ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946000"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="64bc3-102">\<ワークフローの動作 ></span><span class="sxs-lookup"><span data-stu-id="64bc3-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="64bc3-103">この要素には、 **Servicebehaviors**コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64bc3-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="64bc3-104">コレクション内の各要素は、ワークフロー サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="64bc3-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="64bc3-105">各動作要素は、一意の**name**属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="64bc3-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="64bc3-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="64bc3-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64bc3-107">構文</span><span class="sxs-lookup"><span data-stu-id="64bc3-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64bc3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64bc3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64bc3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64bc3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64bc3-110">属性</span><span class="sxs-lookup"><span data-stu-id="64bc3-110">Attributes</span></span>  
 <span data-ttu-id="64bc3-111">なし</span><span class="sxs-lookup"><span data-stu-id="64bc3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="64bc3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="64bc3-112">Child Elements</span></span>  
  
|<span data-ttu-id="64bc3-113">要素</span><span class="sxs-lookup"><span data-stu-id="64bc3-113">Element</span></span>|<span data-ttu-id="64bc3-114">説明</span><span class="sxs-lookup"><span data-stu-id="64bc3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64bc3-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="64bc3-115">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="64bc3-116">この構成セクションは、特定のワークフロー サービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="64bc3-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64bc3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="64bc3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="64bc3-118">要素</span><span class="sxs-lookup"><span data-stu-id="64bc3-118">Element</span></span>|<span data-ttu-id="64bc3-119">説明</span><span class="sxs-lookup"><span data-stu-id="64bc3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64bc3-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="64bc3-120">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="64bc3-121">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="64bc3-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64bc3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="64bc3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="64bc3-123">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="64bc3-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
