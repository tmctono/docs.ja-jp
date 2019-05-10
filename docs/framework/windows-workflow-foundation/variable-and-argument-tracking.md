---
title: 変数と引数の追跡
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: 75ec8124200b146965214d161d0e6f246888542c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640981"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="f39dc-102">変数と引数の追跡</span><span class="sxs-lookup"><span data-stu-id="f39dc-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="f39dc-103">ワークフローの実行を追跡するときは、データを抽出すると便利です。</span><span class="sxs-lookup"><span data-stu-id="f39dc-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="f39dc-104">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="f39dc-105">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] では、追跡を使用して、ワークフローのアクティビティのスコープ内の参照可能な変数や引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="f39dc-106">プロファイルを追跡すると、データを簡単に抽出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f39dc-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="f39dc-107">変数と引数</span><span class="sxs-lookup"><span data-stu-id="f39dc-107">Variables and Arguments</span></span>  
 <span data-ttu-id="f39dc-108">変数および引数が抽出されるのは、アクティビティが ActivityStateRecord を生成したときです。</span><span class="sxs-lookup"><span data-stu-id="f39dc-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="f39dc-109">変数は、アクティビティのスコープ内にある場合にのみ抽出の対象となります。</span><span class="sxs-lookup"><span data-stu-id="f39dc-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="f39dc-110">アクティビティ内に抽出する変数は、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f39dc-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
- <span data-ttu-id="f39dc-111">変数名によって変数が指定されている場合、追跡されている現在のアクティビティと親アクティビティ内の変数が追跡で検索されます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="f39dc-112">変数は、現在のアクティビティのスコープと親スコープ内で検索されます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
- <span data-ttu-id="f39dc-113">抽出される変数名を使用して指定した場合は、="\*"、追跡されている現在のアクティビティ内のすべての変数が抽出されます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-113">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="f39dc-114">この場合、スコープ内の変数でも、親アクティビティで定義されているものは抽出されません。</span><span class="sxs-lookup"><span data-stu-id="f39dc-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="f39dc-115">引数の抽出時、抽出される引数はアクティビティの状態によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f39dc-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="f39dc-116">アクティビティの状態が Executing である場合、`InArguments` のみが抽出に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="f39dc-117">他のアクティビティ状態 (Closed、Faulted、Canceled) については、すべての引数、InArguments と OutArguments の両方が抽出に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="f39dc-118">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="f39dc-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="f39dc-119">変数と引数は、<xref:System.Activities.Tracking.ActivityStateRecord> でのみ抽出できるため、<xref:System.Activities.Tracking.ActivityStateQuery> を使用して追跡プロファイル内で定期受信されます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="f39dc-120">変数および引数に格納される情報の保護</span><span class="sxs-lookup"><span data-stu-id="f39dc-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="f39dc-121">追跡される変数や引数は、既定では WF ランタイムによって参照可能になります。</span><span class="sxs-lookup"><span data-stu-id="f39dc-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="f39dc-122">ワークフローの開発者は、次のような手順を行うことで、追跡対象の変数や引数へのアクセスを防止できます。</span><span class="sxs-lookup"><span data-stu-id="f39dc-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1. <span data-ttu-id="f39dc-123">変数の値を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="f39dc-123">Encrypt the value of a variable.</span></span>  
  
2. <span data-ttu-id="f39dc-124">追跡プロファイルの作成を管理して、変数や引数の抽出を防止します。</span><span class="sxs-lookup"><span data-stu-id="f39dc-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3. <span data-ttu-id="f39dc-125">カスタムの追跡参加要素については、変数や引数に格納されている機密情報が WF コードによって公開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f39dc-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39dc-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f39dc-126">See also</span></span>

- [<span data-ttu-id="f39dc-127">Windows Server App Fabric の監視</span><span class="sxs-lookup"><span data-stu-id="f39dc-127">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="f39dc-128">App Fabric でアプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="f39dc-128">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
