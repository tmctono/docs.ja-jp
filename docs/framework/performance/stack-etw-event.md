---
title: スタック ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: f3014a04ba7cacbe37b6706e2919ffd7de19aa65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715916"
---
# <a name="stack-etw-event"></a><span data-ttu-id="02ea2-102">スタック ETW イベント</span><span class="sxs-lookup"><span data-stu-id="02ea2-102">Stack ETW Event</span></span>
<span data-ttu-id="02ea2-103">イベントの発生後にスタック トレースを生成するには、スタック イベントを他のイベントと併用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02ea2-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="02ea2-104">ランタイム プロバイダーが有効になると、ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="02ea2-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="02ea2-105">これは頻度が非常に高いイベントです。別のランタイム イベントが発生するたびに発生するためです。</span><span class="sxs-lookup"><span data-stu-id="02ea2-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="02ea2-106">そのような理由から、このイベントの使用には注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="02ea2-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="02ea2-107">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="02ea2-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="02ea2-108">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="02ea2-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="02ea2-109">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="02ea2-109">Keyword for raising the event</span></span>|<span data-ttu-id="02ea2-110">レベル</span><span class="sxs-lookup"><span data-stu-id="02ea2-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="02ea2-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="02ea2-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="02ea2-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="02ea2-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="02ea2-113">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="02ea2-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="02ea2-114">Event</span><span class="sxs-lookup"><span data-stu-id="02ea2-114">Event</span></span>|<span data-ttu-id="02ea2-115">イベント ID</span><span class="sxs-lookup"><span data-stu-id="02ea2-115">Event ID</span></span>|<span data-ttu-id="02ea2-116">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="02ea2-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="02ea2-117">82</span><span class="sxs-lookup"><span data-stu-id="02ea2-117">82</span></span>|<span data-ttu-id="02ea2-118">他のイベントを併用し、イベント後にスタック トレースを生成します。</span><span class="sxs-lookup"><span data-stu-id="02ea2-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="02ea2-119">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="02ea2-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="02ea2-120">フィールド名</span><span class="sxs-lookup"><span data-stu-id="02ea2-120">Field name</span></span>|<span data-ttu-id="02ea2-121">データ型</span><span class="sxs-lookup"><span data-stu-id="02ea2-121">Data Type</span></span>|<span data-ttu-id="02ea2-122">説明</span><span class="sxs-lookup"><span data-stu-id="02ea2-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="02ea2-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="02ea2-123">ClrInstanceID</span></span>|<span data-ttu-id="02ea2-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="02ea2-124">win:Uint16</span></span>|<span data-ttu-id="02ea2-125">一意のランタイム識別子。</span><span class="sxs-lookup"><span data-stu-id="02ea2-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="02ea2-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="02ea2-126">Reserved1</span></span>|<span data-ttu-id="02ea2-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="02ea2-127">win:UInt8</span></span>|<span data-ttu-id="02ea2-128">予約済み。</span><span class="sxs-lookup"><span data-stu-id="02ea2-128">Reserved.</span></span>|  
|<span data-ttu-id="02ea2-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="02ea2-129">Reserved2</span></span>|<span data-ttu-id="02ea2-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="02ea2-130">win:UInt8</span></span>|<span data-ttu-id="02ea2-131">予約済み。</span><span class="sxs-lookup"><span data-stu-id="02ea2-131">Reserved.</span></span>|  
|<span data-ttu-id="02ea2-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="02ea2-132">FrameCount</span></span>|<span data-ttu-id="02ea2-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="02ea2-133">win:UInt32</span></span>|<span data-ttu-id="02ea2-134">スタック トレースのフレーム数。</span><span class="sxs-lookup"><span data-stu-id="02ea2-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="02ea2-135">Stack</span><span class="sxs-lookup"><span data-stu-id="02ea2-135">Stack</span></span>|<span data-ttu-id="02ea2-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="02ea2-136">win:Pointer</span></span>|<span data-ttu-id="02ea2-137">命令ポインターの列。</span><span class="sxs-lookup"><span data-stu-id="02ea2-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ea2-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ea2-138">See also</span></span>

- [<span data-ttu-id="02ea2-139">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="02ea2-139">CLR ETW Events</span></span>](clr-etw-events.md)
