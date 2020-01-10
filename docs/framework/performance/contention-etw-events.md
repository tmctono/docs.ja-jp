---
title: 競合 ETW イベント-.NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: 98fc2adcaebe4c9646ab9960f796982681a9015a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716132"
---
# <a name="contention-etw-events"></a><span data-ttu-id="cf71e-102">競合 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="cf71e-102">Contention ETW events</span></span>

<span data-ttu-id="cf71e-103">競合イベントは、ランタイムによって使用される <xref:System.Threading.Monitor?displayProperty=nameWithType> ロックまたはネイティブ ロックの競合が発生するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="cf71e-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="cf71e-104">競合は、あるスレッドが、別のスレッドが保持しているロックを待機しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cf71e-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="cf71e-105">競合イベントが発生するキーワードとイベントのレベルを次の表に示します</span><span class="sxs-lookup"><span data-stu-id="cf71e-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="cf71e-106">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf71e-106">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="cf71e-107">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="cf71e-107">Keyword for raising the event</span></span>|<span data-ttu-id="cf71e-108">レベル</span><span class="sxs-lookup"><span data-stu-id="cf71e-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="cf71e-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="cf71e-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="cf71e-110">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="cf71e-110">Informational (4)</span></span>|

<span data-ttu-id="cf71e-111">次の表に、イベントに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="cf71e-111">The following table shows event information:</span></span>

|<span data-ttu-id="cf71e-112">Event</span><span class="sxs-lookup"><span data-stu-id="cf71e-112">Event</span></span>|<span data-ttu-id="cf71e-113">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cf71e-113">Event ID</span></span>|<span data-ttu-id="cf71e-114">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="cf71e-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="cf71e-115">81</span><span class="sxs-lookup"><span data-stu-id="cf71e-115">81</span></span>|<span data-ttu-id="cf71e-116">競合が開始されたとき。</span><span class="sxs-lookup"><span data-stu-id="cf71e-116">Contention starts.</span></span> <span data-ttu-id="cf71e-117">このイベントには、スレッドがロックの取得を待機する前のスピン時間は含まれません。このイベントが発生するのは、スレッドがロックの取得を待機するときだけです。</span><span class="sxs-lookup"><span data-stu-id="cf71e-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="cf71e-118">91</span><span class="sxs-lookup"><span data-stu-id="cf71e-118">91</span></span>|<span data-ttu-id="cf71e-119">競合が終了したとき。</span><span class="sxs-lookup"><span data-stu-id="cf71e-119">Contention ends.</span></span>|

<span data-ttu-id="cf71e-120">次の表に、イベントデータを示します。</span><span class="sxs-lookup"><span data-stu-id="cf71e-120">The following table shows event data:</span></span>

|<span data-ttu-id="cf71e-121">フィールド名</span><span class="sxs-lookup"><span data-stu-id="cf71e-121">Field name</span></span>|<span data-ttu-id="cf71e-122">[データ型]</span><span class="sxs-lookup"><span data-stu-id="cf71e-122">Data type</span></span>|<span data-ttu-id="cf71e-123">説明</span><span class="sxs-lookup"><span data-stu-id="cf71e-123">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="cf71e-124">フラグ</span><span class="sxs-lookup"><span data-stu-id="cf71e-124">Flags</span></span>|<span data-ttu-id="cf71e-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="cf71e-125">win:UInt8</span></span>|<span data-ttu-id="cf71e-126">マネージドの場合は 0、ネイティブの場合は 1 です。</span><span class="sxs-lookup"><span data-stu-id="cf71e-126">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="cf71e-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cf71e-127">ClrInstanceID</span></span>|<span data-ttu-id="cf71e-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cf71e-128">win:UInt16</span></span>|<span data-ttu-id="cf71e-129">CLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="cf71e-129">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cf71e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf71e-130">See also</span></span>

- [<span data-ttu-id="cf71e-131">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="cf71e-131">CLR ETW Events</span></span>](clr-etw-events.md)
