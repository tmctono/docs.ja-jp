---
title: 競合 ETW イベント-.NET
description: 競合 ETW イベントの詳細を取得します。これは、ランタイムによって使用される、システムのスレッドのロックまたはネイティブロックの競合が発生した場合に発生します。
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309600"
---
# <a name="contention-etw-events"></a><span data-ttu-id="c0686-103">競合 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c0686-103">Contention ETW events</span></span>

<span data-ttu-id="c0686-104">競合イベントは、ランタイムによって使用される <xref:System.Threading.Monitor?displayProperty=nameWithType> ロックまたはネイティブ ロックの競合が発生するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="c0686-104">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="c0686-105">競合は、あるスレッドが、別のスレッドが保持しているロックを待機しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c0686-105">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="c0686-106">競合イベントが発生するキーワードとイベントのレベルを次の表に示します </span><span class="sxs-lookup"><span data-stu-id="c0686-106">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="c0686-107">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0686-107">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="c0686-108">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c0686-108">Keyword for raising the event</span></span>|<span data-ttu-id="c0686-109">レベル</span><span class="sxs-lookup"><span data-stu-id="c0686-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c0686-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="c0686-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="c0686-111">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c0686-111">Informational (4)</span></span>|

<span data-ttu-id="c0686-112">次の表に、イベントに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c0686-112">The following table shows event information:</span></span>

|<span data-ttu-id="c0686-113">Event</span><span class="sxs-lookup"><span data-stu-id="c0686-113">Event</span></span>|<span data-ttu-id="c0686-114">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c0686-114">Event ID</span></span>|<span data-ttu-id="c0686-115">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c0686-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="c0686-116">81</span><span class="sxs-lookup"><span data-stu-id="c0686-116">81</span></span>|<span data-ttu-id="c0686-117">競合が開始されたとき。</span><span class="sxs-lookup"><span data-stu-id="c0686-117">Contention starts.</span></span> <span data-ttu-id="c0686-118">このイベントには、スレッドがロックの取得を待機する前のスピン時間は含まれません。このイベントが発生するのは、スレッドがロックの取得を待機するときだけです。</span><span class="sxs-lookup"><span data-stu-id="c0686-118">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="c0686-119">91</span><span class="sxs-lookup"><span data-stu-id="c0686-119">91</span></span>|<span data-ttu-id="c0686-120">競合が終了したとき。</span><span class="sxs-lookup"><span data-stu-id="c0686-120">Contention ends.</span></span>|

<span data-ttu-id="c0686-121">次の表に、イベントデータを示します。</span><span class="sxs-lookup"><span data-stu-id="c0686-121">The following table shows event data:</span></span>

|<span data-ttu-id="c0686-122">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c0686-122">Field name</span></span>|<span data-ttu-id="c0686-123">データ型</span><span class="sxs-lookup"><span data-stu-id="c0686-123">Data type</span></span>|<span data-ttu-id="c0686-124">説明</span><span class="sxs-lookup"><span data-stu-id="c0686-124">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c0686-125">Flags</span><span class="sxs-lookup"><span data-stu-id="c0686-125">Flags</span></span>|<span data-ttu-id="c0686-126">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="c0686-126">win:UInt8</span></span>|<span data-ttu-id="c0686-127">マネージドの場合は 0、ネイティブの場合は 1 です。</span><span class="sxs-lookup"><span data-stu-id="c0686-127">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="c0686-128">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c0686-128">ClrInstanceID</span></span>|<span data-ttu-id="c0686-129">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c0686-129">win:UInt16</span></span>|<span data-ttu-id="c0686-130">CLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c0686-130">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c0686-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0686-131">See also</span></span>

- [<span data-ttu-id="c0686-132">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c0686-132">CLR ETW Events</span></span>](clr-etw-events.md)
