---
title: 移行のガイドライン
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 45f81b29f63701f690e396de2e9834f9933fd775
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796802"
---
# <a name="migration-guidance"></a><span data-ttu-id="295b1-102">移行のガイドライン</span><span class="sxs-lookup"><span data-stu-id="295b1-102">Migration Guidance</span></span>
<span data-ttu-id="295b1-103">[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]では、Microsoft は、Windows Workflow Foundation (WF) の2番目のメジャーバージョンをリリースしています。</span><span class="sxs-lookup"><span data-stu-id="295b1-103">In the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], Microsoft is releasing the second major version of Windows Workflow Foundation (WF).</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="295b1-104">は WinFX でリリースされました (これには WF3 の型\*が含まれています)。また、で[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]も強化されました。</span><span class="sxs-lookup"><span data-stu-id="295b1-104">was released in WinFX (this included the types in the System.Workflow.\* namespaces; now referred to as WF3) and enhanced in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="295b1-105">WF3 は、 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]の一部でもありますが、新しいワークフローテクノロジ (WF4 と呼ばれる型\* ) と共に存在します。</span><span class="sxs-lookup"><span data-stu-id="295b1-105">WF3 is also part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], but it exists there alongside new workflow technology (the types in the System.Activities.\* namespaces; referred to as WF4).</span></span> <span data-ttu-id="295b1-106">WF4 の導入時期を検討する場合は、最初にそのタイミングの管理を認識することが重要です。</span><span class="sxs-lookup"><span data-stu-id="295b1-106">When considering when to adopt WF4, it is important to first recognize that you control the timing.</span></span>  
  
- <span data-ttu-id="295b1-107">WF3 は [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] で完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="295b1-107">WF3 is a fully supported part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span>  
  
- <span data-ttu-id="295b1-108">WF3 のアプリケーションは、変更しなくても [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] で実行され、引き続き完全にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="295b1-108">WF3 applications run on the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] without modification and continue to be fully supported.</span></span>  
  
- <span data-ttu-id="295b1-109">新しい WF3 アプリケーションを作成し、既存のアプリケーションを Visual Studio 2012 で編集し、完全にサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="295b1-109">New WF3 applications can be created and your existing applications can be edited in Visual Studio 2012 and are fully supported.</span></span>  
  
 <span data-ttu-id="295b1-110">したがって、.NET Framework 4 を採用するかどうかの決定は、WF3 (\*\*WF4) から () に移動するかどうかを決定するものとは分離されています。</span><span class="sxs-lookup"><span data-stu-id="295b1-110">Thus, the decision to adopt the .NET Framework 4 is decoupled from your decision to move to WF4 (System.Activities.\*) from WF3 (System.Workflow.\*).</span></span> <span data-ttu-id="295b1-111">このトピックでは、WF の移行のガイドラインへのリンクを提供し、WF3 および WF4 での作業に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="295b1-111">This topic provides links to WF migration guidance that provides information about working with WF3 and WF4.</span></span>  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a><span data-ttu-id="295b1-112">WF の移行に関するホワイト ペーパーとクックブック</span><span class="sxs-lookup"><span data-stu-id="295b1-112">WF Migration Whitepapers and Cookbooks</span></span>  
 <span data-ttu-id="295b1-113">[WF の移行の概要](https://go.microsoft.com/fwlink/?LinkId=153873)に関するトピックでは、WF3 と WF4 の間の関係と移行戦略の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-113">The [WF Migration Overview](https://go.microsoft.com/fwlink/?LinkId=153873) topic provides a broad overview of the relationship between WF3 and WF4 and migration strategies.</span></span> <span data-ttu-id="295b1-114">関連トピックでは、特定のトピックを掘り下げて説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-114">Companion topics drill into specific topics.</span></span>  
  
 [<span data-ttu-id="295b1-115">WF の移行の概要</span><span class="sxs-lookup"><span data-stu-id="295b1-115">WF Migration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=153873)  
 <span data-ttu-id="295b1-116">WF3 と WF4 の関係、および .NET 4 のワークフロー テクノロジのユーザーまたは潜在的なユーザーとして使用できる選択肢について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-116">Describes the relationship between WF3 and WF4, and the choices you have as a user or a potential user of workflow technology in .NET 4.</span></span>  
  
 [<span data-ttu-id="295b1-117">WF の移行:WF3 開発のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="295b1-117">WF Migration: Best Practices for WF3 Development</span></span>](https://go.microsoft.com/fwlink/?LinkId=153852)  
 <span data-ttu-id="295b1-118">より簡単に WF4 に移行できるように、WF3 の成果物を設計する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-118">Discusses how to design WF3 artifacts so they can be more easily migrated to WF4.</span></span>  
  
 [<span data-ttu-id="295b1-119">WF のガイダンス:ロジック</span><span class="sxs-lookup"><span data-stu-id="295b1-119">WF Guidance: Rules</span></span>](https://go.microsoft.com/fwlink/?LinkId=153854)  
 <span data-ttu-id="295b1-120">[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] のソリューションに規則関連の投資を促進する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-120">Discusses how to bring rules-related investments forward into [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] solutions.</span></span>  
  
 [<span data-ttu-id="295b1-121">WF のガイダンス:ステートマシン</span><span class="sxs-lookup"><span data-stu-id="295b1-121">WF Guidance: State Machine</span></span>](https://go.microsoft.com/fwlink/?LinkId=153855)  
 <span data-ttu-id="295b1-122">ステート マシンのアクティビティがない場合の WF4 の制御フロー モデリングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-122">Discusses WF4 control flow modeling in the absence of a State-Machine activity.</span></span>  
  
 <span data-ttu-id="295b1-123">このガイダンスは、.NET Framework 4 を対象とするワークフロー プロジェクトにのみ該当することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="295b1-123">Note that this guidance only applies to workflow projects that target .NET Framework 4.</span></span> <span data-ttu-id="295b1-124">ステート マシンのワークフローは、Platform Update 1 のリリースで .NET 4.0.1 に追加され、.NET Framework 4.5 の一部として含まれていました。</span><span class="sxs-lookup"><span data-stu-id="295b1-124">State Machine workflows were added in .NET 4.0.1 with the release of Platform Update 1, and were included as part of .NET Framework 4.5.</span></span> <span data-ttu-id="295b1-125">.NET 4.0.1-4.0.3 および .NET Framework 4.5 でのステートマシンワークフローの詳細については、「 [Update 4.0.1 for Microsoft .NET Framework 4 Features](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) And [state machine ワークフロー](state-machine-workflows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="295b1-125">For more information about state machine workflows in .NET 4.0.1 - 4.0.3 and .NET Framework 4.5, see [Update 4.0.1 for Microsoft .NET Framework 4 Features](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) and [State Machine Workflows](state-machine-workflows.md).</span></span>  
  
 [<span data-ttu-id="295b1-126">WF の移行のクックブック:カスタムアクティビティ</span><span class="sxs-lookup"><span data-stu-id="295b1-126">WF Migration Cookbook: Custom Activities</span></span>](https://go.microsoft.com/fwlink/?LinkId=153856)  
 <span data-ttu-id="295b1-127">WF3 のカスタム アクティビティを WF4 で再設計する場合のサンプルと手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-127">Provides examples and instructions for redesigning WF3 custom activities on WF4.</span></span>  
  
 [<span data-ttu-id="295b1-128">WF の移行のクックブック:高度なカスタムアクティビティ</span><span class="sxs-lookup"><span data-stu-id="295b1-128">WF Migration Cookbook: Advanced Custom Activities</span></span>](https://go.microsoft.com/fwlink/?LinkId=275560)  
 <span data-ttu-id="295b1-129">WF3 キューを使用して子アクティビティを WF4 カスタム アクティビティとしてスケジュールする高度な WF3 カスタム アクティビティを再設計するための指針を示します。</span><span class="sxs-lookup"><span data-stu-id="295b1-129">Provides guidance for redesigning advanced WF3 custom activities that use WF3 queues and schedule child activities as WF4 custom activities.</span></span>  
  
 [<span data-ttu-id="295b1-130">WF の移行のクックブック:コンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="295b1-130">WF Migration Cookbook: Workflows</span></span>](https://go.microsoft.com/fwlink/?LinkId=153858)  
 <span data-ttu-id="295b1-131">WF3 のワークフローを WF4 で再設計する場合のサンプルと手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="295b1-131">Provides examples and instructions for redesigning WF3 workflows on WF4.</span></span>  
  
 [<span data-ttu-id="295b1-132">WF の移行のクックブック:ワークフローのホスト</span><span class="sxs-lookup"><span data-stu-id="295b1-132">WF Migration Cookbook: Workflow Hosting</span></span>](https://go.microsoft.com/fwlink/?LinkId=275561)  
 <span data-ttu-id="295b1-133">WF3 ホスティング コードを WF4 ホスティング コードとして再設計するための指針を示します。</span><span class="sxs-lookup"><span data-stu-id="295b1-133">Provides guidance for redesigning WF3 hosting code as WF4 hosting code.</span></span> <span data-ttu-id="295b1-134">この目的は、WF3 と WF4 のワークフロー ホスティングの主な違いを説明することです。</span><span class="sxs-lookup"><span data-stu-id="295b1-134">The goal is to cover the key differences in workflow hosting between WF3 and WF4.</span></span>  
  
 [<span data-ttu-id="295b1-135">WF の移行のクックブック:ワークフローの追跡</span><span class="sxs-lookup"><span data-stu-id="295b1-135">WF Migration Cookbook: Workflow Tracking</span></span>](https://go.microsoft.com/fwlink/?LinkId=275562)  
 <span data-ttu-id="295b1-136">WF3 追跡コードを再設計するための指針と、同等の WF4 追跡コードと構成を使用した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="295b1-136">Provides guidance for redesigning WF3 tracking code and configuration using equivalent WF4 tracking code and configuration.</span></span>  
  
 [<span data-ttu-id="295b1-137">WF のガイダンス:ワークフローサービス</span><span class="sxs-lookup"><span data-stu-id="295b1-137">WF Guidance: Workflow Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=275564)  
 <span data-ttu-id="295b1-138">事前定義アクティビティの一般的なシナリオ向けに、WF3 で作成した Windows Communication Foundation (WCF) Web サービス (一般にワークフロー サービスと呼ばれます) を実装するワークフローを WF4 を使用するように再設計するための詳細な手順を例を中心として示します。</span><span class="sxs-lookup"><span data-stu-id="295b1-138">Provides example-oriented step-by-step instructions for redesigning workflows that implement Windows Communication Foundation (WCF) web services (commonly referred to as workflow services) created in WF3 to use WF4, for common scenarios for out-of-box activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295b1-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="295b1-139">See also</span></span>

- <xref:System.Activities.Statements.Interop>
