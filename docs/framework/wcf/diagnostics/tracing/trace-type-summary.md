---
title: トレースの種類の概要
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674836"
---
# <a name="trace-type-summary"></a><span data-ttu-id="a39f3-102">トレースの種類の概要</span><span class="sxs-lookup"><span data-stu-id="a39f3-102">Trace Type Summary</span></span>
<span data-ttu-id="a39f3-103">[ソースレベルは](xref:System.Diagnostics.SourceLevels)、さまざまなトレースレベルを定義します:クリティカル、エラー、警告、情報、および詳細、およびトレース境界とアクティビティ転送`ActivityTracing`イベントの出力を切り替えるフラグの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="a39f3-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="a39f3-104">から出力できるトレース<xref:System.Diagnostics.TraceEventType>の種類を確認することもできます<xref:System.Diagnostics>。</span><span class="sxs-lookup"><span data-stu-id="a39f3-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="a39f3-105">最も重要な種類を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="a39f3-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="a39f3-106">トレースの種類</span><span class="sxs-lookup"><span data-stu-id="a39f3-106">Trace Type</span></span>|<span data-ttu-id="a39f3-107">説明</span><span class="sxs-lookup"><span data-stu-id="a39f3-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="a39f3-108">Critical</span><span class="sxs-lookup"><span data-stu-id="a39f3-108">Critical</span></span>|<span data-ttu-id="a39f3-109">致命的なエラーまたはアプリケーションのクラッシュ。</span><span class="sxs-lookup"><span data-stu-id="a39f3-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="a39f3-110">エラー</span><span class="sxs-lookup"><span data-stu-id="a39f3-110">Error</span></span>|<span data-ttu-id="a39f3-111">回復可能なエラー。</span><span class="sxs-lookup"><span data-stu-id="a39f3-111">Recoverable error.</span></span>|  
|<span data-ttu-id="a39f3-112">警告</span><span class="sxs-lookup"><span data-stu-id="a39f3-112">Warning</span></span>|<span data-ttu-id="a39f3-113">情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="a39f3-113">Informational message.</span></span>|  
|<span data-ttu-id="a39f3-114">Information</span><span class="sxs-lookup"><span data-stu-id="a39f3-114">Information</span></span>|<span data-ttu-id="a39f3-115">重大ではない問題。</span><span class="sxs-lookup"><span data-stu-id="a39f3-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="a39f3-116">"詳細"</span><span class="sxs-lookup"><span data-stu-id="a39f3-116">Verbose</span></span>|<span data-ttu-id="a39f3-117">トレースのデバッグ。</span><span class="sxs-lookup"><span data-stu-id="a39f3-117">Debugging trace.</span></span>|  
|<span data-ttu-id="a39f3-118">[開始]</span><span class="sxs-lookup"><span data-stu-id="a39f3-118">Start</span></span>|<span data-ttu-id="a39f3-119">処理の論理単位の開始。</span><span class="sxs-lookup"><span data-stu-id="a39f3-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a39f3-120">[中断]</span><span class="sxs-lookup"><span data-stu-id="a39f3-120">Suspend</span></span>|<span data-ttu-id="a39f3-121">処理の論理単位の中断。</span><span class="sxs-lookup"><span data-stu-id="a39f3-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a39f3-122">Resume</span><span class="sxs-lookup"><span data-stu-id="a39f3-122">Resume</span></span>|<span data-ttu-id="a39f3-123">処理の論理単位の再開。</span><span class="sxs-lookup"><span data-stu-id="a39f3-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a39f3-124">Stop</span><span class="sxs-lookup"><span data-stu-id="a39f3-124">Stop</span></span>|<span data-ttu-id="a39f3-125">処理の論理単位の停止。</span><span class="sxs-lookup"><span data-stu-id="a39f3-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="a39f3-126">転送</span><span class="sxs-lookup"><span data-stu-id="a39f3-126">Transfer</span></span>|<span data-ttu-id="a39f3-127">相関 ID の変更。</span><span class="sxs-lookup"><span data-stu-id="a39f3-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="a39f3-128">アクティビティは、上記のトレースの種類の組み合わせとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="a39f3-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="a39f3-129">ローカル (トレース ソース) スコープでの典型的なアクティビティを定義する正規表現は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a39f3-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="a39f3-130">これは、アクティビティが次の条件を満たす必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a39f3-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="a39f3-131">アクティビティは、Start トレースによって開始し、Stop トレースによって停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39f3-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="a39f3-132">Suspend トレースまたは Resume トレースの直前に Transfer トレースが必要です。</span><span class="sxs-lookup"><span data-stu-id="a39f3-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="a39f3-133">Suspend トレースと Resume トレースが存在する場合、これらのトレースの間にトレースが存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="a39f3-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="a39f3-134">上記の条件を満たしている限り、Critical/Error/Warning/Information/Verbose/Transfer の各トレースはいくつでも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a39f3-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="a39f3-135">グローバル スコープでの典型的なアクティビティを定義する正規表現は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a39f3-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="a39f3-136">R はローカル スコープのアクティビティを表す正規表現です。</span><span class="sxs-lookup"><span data-stu-id="a39f3-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="a39f3-137">これは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a39f3-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
