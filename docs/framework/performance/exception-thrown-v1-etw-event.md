---
title: Exception Thrown_V1 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447629"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="486b9-102">Exception Thrown_V1 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="486b9-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="486b9-103">このイベントは、スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="486b9-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="486b9-104">イベントが発生するキーワードとイベントのレベルを次の表に示します</span><span class="sxs-lookup"><span data-stu-id="486b9-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="486b9-105">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="486b9-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="486b9-106">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="486b9-106">Keyword for raising the event</span></span>|<span data-ttu-id="486b9-107">レベル</span><span class="sxs-lookup"><span data-stu-id="486b9-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="486b9-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="486b9-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="486b9-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="486b9-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="486b9-110">次の表にイベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="486b9-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="486b9-111">event</span><span class="sxs-lookup"><span data-stu-id="486b9-111">Event</span></span>|<span data-ttu-id="486b9-112">イベント ID</span><span class="sxs-lookup"><span data-stu-id="486b9-112">Event ID</span></span>|<span data-ttu-id="486b9-113">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="486b9-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="486b9-114">80</span><span class="sxs-lookup"><span data-stu-id="486b9-114">80</span></span>|<span data-ttu-id="486b9-115">マネージド例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="486b9-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="486b9-116">次の表にイベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="486b9-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="486b9-117">フィールド名</span><span class="sxs-lookup"><span data-stu-id="486b9-117">Field name</span></span>|<span data-ttu-id="486b9-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="486b9-118">Data type</span></span>|<span data-ttu-id="486b9-119">説明</span><span class="sxs-lookup"><span data-stu-id="486b9-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="486b9-120">例外の種類</span><span class="sxs-lookup"><span data-stu-id="486b9-120">Exception Type</span></span>|<span data-ttu-id="486b9-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="486b9-121">win:UnicodeString</span></span>|<span data-ttu-id="486b9-122">例外の種類 (`System.NullReferenceException` など)。</span><span class="sxs-lookup"><span data-stu-id="486b9-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="486b9-123">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="486b9-123">Exception Message</span></span>|<span data-ttu-id="486b9-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="486b9-124">win:UnicodeString</span></span>|<span data-ttu-id="486b9-125">実際の例外メッセージ。</span><span class="sxs-lookup"><span data-stu-id="486b9-125">Actual exception message.</span></span>|  
|<span data-ttu-id="486b9-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="486b9-126">EIPCodeThrow</span></span>|<span data-ttu-id="486b9-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="486b9-127">win:Pointer</span></span>|<span data-ttu-id="486b9-128">例外が発生した命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="486b9-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="486b9-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="486b9-129">ExceptionHR</span></span>|<span data-ttu-id="486b9-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="486b9-130">win:UInt32</span></span>|<span data-ttu-id="486b9-131">例外 [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)。</span><span class="sxs-lookup"><span data-stu-id="486b9-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="486b9-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="486b9-132">ExceptionFlags</span></span>|<span data-ttu-id="486b9-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="486b9-133">win:UInt16</span></span>|<span data-ttu-id="486b9-134">0x01: HasInnerException (Visual Basic のドキュメントで「[CLR ETW イベント](clr-etw-events.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="486b9-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="486b9-135">0x02: IsNestedException。</span><span class="sxs-lookup"><span data-stu-id="486b9-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="486b9-136">0x04: IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="486b9-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="486b9-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="486b9-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="486b9-138">0x10: IsCLSCompliant (<xref:System.Exception> から派生した例外は CLS 準拠で、それ以外は CLS 非準拠)。</span><span class="sxs-lookup"><span data-stu-id="486b9-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="486b9-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="486b9-139">ClrInstanceID</span></span>|<span data-ttu-id="486b9-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="486b9-140">win:UInt16</span></span>|<span data-ttu-id="486b9-141">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="486b9-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="486b9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="486b9-142">See also</span></span>

- [<span data-ttu-id="486b9-143">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="486b9-143">CLR ETW Events</span></span>](clr-etw-events.md)
