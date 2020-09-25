---
title: <behaviors> ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 21974f77526f55a47c014a285efd3bbac6fc1f7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189605"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="e2155-102">\<behaviors> ワークフローの</span><span class="sxs-lookup"><span data-stu-id="e2155-102">\<behaviors> of workflow</span></span>

<span data-ttu-id="e2155-103">この要素には、 **Servicebehaviors** コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2155-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="e2155-104">コレクション内の各要素は、ワークフロー サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2155-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="e2155-105">各動作要素は、一意の **name** 属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="e2155-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="e2155-106">構文</span><span class="sxs-lookup"><span data-stu-id="e2155-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2155-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e2155-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e2155-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2155-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2155-109">属性</span><span class="sxs-lookup"><span data-stu-id="e2155-109">Attributes</span></span>  

 <span data-ttu-id="e2155-110">None</span><span class="sxs-lookup"><span data-stu-id="e2155-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2155-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e2155-111">Child Elements</span></span>  
  
|<span data-ttu-id="e2155-112">要素</span><span class="sxs-lookup"><span data-stu-id="e2155-112">Element</span></span>|<span data-ttu-id="e2155-113">説明</span><span class="sxs-lookup"><span data-stu-id="e2155-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="e2155-114">この構成セクションは、特定のワークフロー サービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="e2155-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2155-115">親要素</span><span class="sxs-lookup"><span data-stu-id="e2155-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e2155-116">要素</span><span class="sxs-lookup"><span data-stu-id="e2155-116">Element</span></span>|<span data-ttu-id="e2155-117">説明</span><span class="sxs-lookup"><span data-stu-id="e2155-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="e2155-118">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="e2155-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2155-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2155-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="e2155-120">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="e2155-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
