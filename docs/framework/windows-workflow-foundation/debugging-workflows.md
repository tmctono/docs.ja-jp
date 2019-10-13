---
title: デバッグのワークフロー
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 3947e61161b0e2108fa48fbc7e33fb7601645a1b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291488"
---
# <a name="debugging-workflows"></a><span data-ttu-id="520f6-102">デバッグのワークフロー</span><span class="sxs-lookup"><span data-stu-id="520f6-102">Debugging Workflows</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="520f6-103">には、開発環境から実行中のワークフローをデバッグするオプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="520f6-103">offers several options for debugging running workflows from the development environment.</span></span> <span data-ttu-id="520f6-104">ワークフローは、デザイナー、XAML、およびコードでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="520f6-104">Workflows can be debugged in the designer, in XAML, and in code.</span></span>

## <a name="debugging-in-the-workflow-designer"></a><span data-ttu-id="520f6-105">ワークフロー デザイナーでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="520f6-105">Debugging in the Workflow Designer</span></span>

<span data-ttu-id="520f6-106">ワークフローデザイナーのアクティビティにブレークポイントを設定するには、アクティビティを強調表示し、 <kbd>F9</kbd>キーを押すか、アクティビティのコンテキストメニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="520f6-106">Breakpoints can be set on activities in the workflow designer by either highlighting the activity and pressing <kbd>F9</kbd> or by using the activity’s context menu.</span></span> <span data-ttu-id="520f6-107">ワークフロー ホストをデバッグ モードで実行すると、ワークフローの実行は一時停止します。</span><span class="sxs-lookup"><span data-stu-id="520f6-107">Execution of the workflow then breaks when the workflow host is run in debug mode.</span></span> <span data-ttu-id="520f6-108">次のスクリーンショットでは、ワークフローの実行はブレークポイントで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="520f6-108">In the following screenshot, workflow execution is paused at a breakpoint.</span></span> <span data-ttu-id="520f6-109">詳細については、「[ワークフローデザイナーを使用したワークフローのデバッグ](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f6-109">For more information, see [Debugging Workflows with the Workflow Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).</span></span>

## <a name="debugging-in-xaml"></a><span data-ttu-id="520f6-110">XAML でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="520f6-110">Debugging in XAML</span></span>

<span data-ttu-id="520f6-111">デザイナーでワークフローがブレークポイントで一時停止すると、XAML でもワークフローをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="520f6-111">If a workflow has paused at a breakpoint in the designer, the workflow can also be debugged in XAML.</span></span> <span data-ttu-id="520f6-112">XAML での実行ポイントを表示するには、ワークフローの実行が一時停止されているときに、ワークフローデザイナーで **[Xaml ビュー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="520f6-112">To view the point of execution in XAML, select **XAML View** in the workflow designer when workflow execution is paused.</span></span> <span data-ttu-id="520f6-113">デバッグをデザイナーに切り替えるには、ソリューション エクスプローラーからデザイナーでワークフローを開き直します。</span><span class="sxs-lookup"><span data-stu-id="520f6-113">Debugging can be switched back to the designer by re-opening the workflow in the designer from the solution explorer.</span></span> <span data-ttu-id="520f6-114">詳細については、「[方法 :ワークフローデザイナー @ no__t-0 を使用して XAML をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="520f6-114">For more information, see [How to: Debug XAML with the Workflow Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).</span></span>

## <a name="debugging-in-code"></a><span data-ttu-id="520f6-115">コードでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="520f6-115">Debugging in Code</span></span>

<span data-ttu-id="520f6-116">ブレークポイントを設定するには、コードペインの左余白をクリックするか、カーソルを設定する行にカーソルを合わせて<kbd>F9</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="520f6-116">To set a breakpoint, click the left margin of the code pane, or press <kbd>F9</kbd> with the cursor at the line where you want to set it.</span></span>

## <a name="attaching-to-a-workflow-process"></a><span data-ttu-id="520f6-117">ワークフロー プロセスへのアタッチ</span><span class="sxs-lookup"><span data-stu-id="520f6-117">Attaching to a Workflow Process</span></span>

<span data-ttu-id="520f6-118">ワークフローのデバッグは、Visual Studio のインフラストラクチャを使用したプロセスへのアタッチもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="520f6-118">Workflow debugging also supports using Visual Studio’s infrastructure to attach to a process.</span></span> <span data-ttu-id="520f6-119">そのため、ワークフロー作成者は、Internet Information Services (IIS) 7.0 など異なるホスト環境で実行されているワークフローをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="520f6-119">This enables the workflow author to debug a workflow running in a different host environment such as Internet Information Services (IIS) 7.0.</span></span>

## <a name="remote-debugging"></a><span data-ttu-id="520f6-120">Remote Debugging</span><span class="sxs-lookup"><span data-stu-id="520f6-120">Remote Debugging</span></span>

<span data-ttu-id="520f6-121">Windows Workflow Foundation (WF) リモートデバッグは、他の Visual Studio コンポーネントのリモートデバッグと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="520f6-121">Windows Workflow Foundation (WF) remote debugging functions the same as remote debugging for other Visual Studio components.</span></span> <span data-ttu-id="520f6-122">リモートデバッグの使用方法の詳細については、@no__t を参照してください。リモートデバッグ @ no__t を有効にします。</span><span class="sxs-lookup"><span data-stu-id="520f6-122">For information on using remote debugging, see [How to: Enable Remote Debugging](https://go.microsoft.com/fwlink/?LinkId=196257).</span></span>

> [!NOTE]
> <span data-ttu-id="520f6-123">ワークフローアプリケーションが x86 アーキテクチャを対象としていて、64ビットオペレーティングシステムを実行しているコンピューターでホストされている場合、リモートコンピューターに Visual Studio がインストールされていない場合、またはワークフローアプリケーションのターゲットがに変更されている場合を除き、リモートデバッグは機能しません。**任意の CPU**。</span><span class="sxs-lookup"><span data-stu-id="520f6-123">If the workflow application targets the x86 architecture and is hosted on a computer running a 64 bit operating system, then remote debugging will not work unless Visual Studio is installed on the remote computer or the target for the workflow application is changed to **Any CPU**.</span></span>

## <a name="extending-the-workflow-debugging-service"></a><span data-ttu-id="520f6-124">ワークフロー デバッグ サービスの拡張</span><span class="sxs-lookup"><span data-stu-id="520f6-124">Extending the Workflow Debugging Service</span></span>

<span data-ttu-id="520f6-125">ワークフロー デバッガー サービスは公開されるようになり、ホストを変更したデザイナーでのモニタリング、シミュレーション、デバッグなど、カスタム アプリケーションを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="520f6-125">The workflow debugger service is now public and can be used to create custom applications such as monitoring, simulation, and debugging in a re-hosted designer.</span></span> <span data-ttu-id="520f6-126">詳細については、「<xref:System.Activities.Presentation.Debug.DebuggerService>」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f6-126">For more information, see the <xref:System.Activities.Presentation.Debug.DebuggerService> article.</span></span>
