---
title: スタック ETW イベント
description: Stack ETW イベントについて説明します。これは、イベントの発生後にスタックトレースを生成するために、他のイベントと組み合わせて使用する必要があります。
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474138"
---
# <a name="stack-etw-event"></a><span data-ttu-id="28345-103">スタック ETW イベント</span><span class="sxs-lookup"><span data-stu-id="28345-103">Stack ETW Event</span></span>
<span data-ttu-id="28345-104">イベントの発生後にスタック トレースを生成するには、スタック イベントを他のイベントと併用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28345-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="28345-105">ランタイム プロバイダーが有効になると、ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="28345-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="28345-106">これは頻度が非常に高いイベントです。別のランタイム イベントが発生するたびに発生するためです。</span><span class="sxs-lookup"><span data-stu-id="28345-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="28345-107">そのような理由から、このイベントの使用には注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="28345-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="28345-108">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="28345-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="28345-109">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="28345-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="28345-110">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="28345-110">Keyword for raising the event</span></span>|<span data-ttu-id="28345-111">Level</span><span class="sxs-lookup"><span data-stu-id="28345-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="28345-112">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="28345-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="28345-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="28345-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="28345-114">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="28345-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="28345-115">Event</span><span class="sxs-lookup"><span data-stu-id="28345-115">Event</span></span>|<span data-ttu-id="28345-116">イベント ID</span><span class="sxs-lookup"><span data-stu-id="28345-116">Event ID</span></span>|<span data-ttu-id="28345-117">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="28345-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="28345-118">82</span><span class="sxs-lookup"><span data-stu-id="28345-118">82</span></span>|<span data-ttu-id="28345-119">他のイベントを併用し、イベント後にスタック トレースを生成します。</span><span class="sxs-lookup"><span data-stu-id="28345-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="28345-120">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="28345-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="28345-121">フィールド名</span><span class="sxs-lookup"><span data-stu-id="28345-121">Field name</span></span>|<span data-ttu-id="28345-122">データ型</span><span class="sxs-lookup"><span data-stu-id="28345-122">Data Type</span></span>|<span data-ttu-id="28345-123">説明</span><span class="sxs-lookup"><span data-stu-id="28345-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="28345-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="28345-124">ClrInstanceID</span></span>|<span data-ttu-id="28345-125">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="28345-125">win:Uint16</span></span>|<span data-ttu-id="28345-126">一意のランタイム識別子。</span><span class="sxs-lookup"><span data-stu-id="28345-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="28345-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="28345-127">Reserved1</span></span>|<span data-ttu-id="28345-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="28345-128">win:UInt8</span></span>|<span data-ttu-id="28345-129">予約済み。</span><span class="sxs-lookup"><span data-stu-id="28345-129">Reserved.</span></span>|  
|<span data-ttu-id="28345-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="28345-130">Reserved2</span></span>|<span data-ttu-id="28345-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="28345-131">win:UInt8</span></span>|<span data-ttu-id="28345-132">予約済み。</span><span class="sxs-lookup"><span data-stu-id="28345-132">Reserved.</span></span>|  
|<span data-ttu-id="28345-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="28345-133">FrameCount</span></span>|<span data-ttu-id="28345-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="28345-134">win:UInt32</span></span>|<span data-ttu-id="28345-135">スタック トレースのフレーム数。</span><span class="sxs-lookup"><span data-stu-id="28345-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="28345-136">スタック</span><span class="sxs-lookup"><span data-stu-id="28345-136">Stack</span></span>|<span data-ttu-id="28345-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="28345-137">win:Pointer</span></span>|<span data-ttu-id="28345-138">命令ポインターの列。</span><span class="sxs-lookup"><span data-stu-id="28345-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28345-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="28345-139">See also</span></span>

- [<span data-ttu-id="28345-140">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="28345-140">CLR ETW Events</span></span>](clr-etw-events.md)
