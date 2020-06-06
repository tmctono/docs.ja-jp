---
title: <customTrackingQueries>WCF の
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855439"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="7b697-102">\<customTrackingQueries>WCF の</span><span class="sxs-lookup"><span data-stu-id="7b697-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="7b697-103">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b697-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7b697-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b697-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="7b697-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b697-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="7b697-106">構文</span><span class="sxs-lookup"><span data-stu-id="7b697-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b697-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7b697-107">Attributes and elements</span></span>

<span data-ttu-id="7b697-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b697-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b697-109">属性</span><span class="sxs-lookup"><span data-stu-id="7b697-109">Attributes</span></span>

<span data-ttu-id="7b697-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7b697-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="7b697-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7b697-111">Child elements</span></span>
  
|<span data-ttu-id="7b697-112">要素</span><span class="sxs-lookup"><span data-stu-id="7b697-112">Element</span></span>|<span data-ttu-id="7b697-113">説明</span><span class="sxs-lookup"><span data-stu-id="7b697-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="7b697-114">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="7b697-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b697-115">親要素</span><span class="sxs-lookup"><span data-stu-id="7b697-115">Parent elements</span></span>  
  
|<span data-ttu-id="7b697-116">要素</span><span class="sxs-lookup"><span data-stu-id="7b697-116">Element</span></span>|<span data-ttu-id="7b697-117">説明</span><span class="sxs-lookup"><span data-stu-id="7b697-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="7b697-118">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="7b697-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b697-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b697-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7b697-120">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7b697-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7b697-121">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7b697-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
