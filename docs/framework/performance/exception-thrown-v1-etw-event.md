---
title: Exception Thrown_V1 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: 80faf6e607755ee79c7ec17f2d7d3d5bdce822b7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716059"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="04d65-102">Exception Thrown_V1 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="04d65-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="04d65-103">このイベントは、スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="04d65-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="04d65-104">イベントが発生するキーワードとイベントのレベルを次の表に示します</span><span class="sxs-lookup"><span data-stu-id="04d65-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="04d65-105">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04d65-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="04d65-106">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="04d65-106">Keyword for raising the event</span></span>|<span data-ttu-id="04d65-107">レベル</span><span class="sxs-lookup"><span data-stu-id="04d65-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="04d65-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="04d65-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="04d65-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="04d65-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="04d65-110">次の表にイベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="04d65-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="04d65-111">Event</span><span class="sxs-lookup"><span data-stu-id="04d65-111">Event</span></span>|<span data-ttu-id="04d65-112">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04d65-112">Event ID</span></span>|<span data-ttu-id="04d65-113">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="04d65-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="04d65-114">80</span><span class="sxs-lookup"><span data-stu-id="04d65-114">80</span></span>|<span data-ttu-id="04d65-115">マネージド例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="04d65-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="04d65-116">次の表にイベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="04d65-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="04d65-117">フィールド名</span><span class="sxs-lookup"><span data-stu-id="04d65-117">Field name</span></span>|<span data-ttu-id="04d65-118">[データ型]</span><span class="sxs-lookup"><span data-stu-id="04d65-118">Data type</span></span>|<span data-ttu-id="04d65-119">説明</span><span class="sxs-lookup"><span data-stu-id="04d65-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="04d65-120">例外の種類</span><span class="sxs-lookup"><span data-stu-id="04d65-120">Exception Type</span></span>|<span data-ttu-id="04d65-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04d65-121">win:UnicodeString</span></span>|<span data-ttu-id="04d65-122">例外の種類 (`System.NullReferenceException` など)。</span><span class="sxs-lookup"><span data-stu-id="04d65-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="04d65-123">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="04d65-123">Exception Message</span></span>|<span data-ttu-id="04d65-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04d65-124">win:UnicodeString</span></span>|<span data-ttu-id="04d65-125">実際の例外メッセージ。</span><span class="sxs-lookup"><span data-stu-id="04d65-125">Actual exception message.</span></span>|  
|<span data-ttu-id="04d65-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="04d65-126">EIPCodeThrow</span></span>|<span data-ttu-id="04d65-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="04d65-127">win:Pointer</span></span>|<span data-ttu-id="04d65-128">例外が発生した命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="04d65-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="04d65-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="04d65-129">ExceptionHR</span></span>|<span data-ttu-id="04d65-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="04d65-130">win:UInt32</span></span>|<span data-ttu-id="04d65-131">例外 [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)。</span><span class="sxs-lookup"><span data-stu-id="04d65-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="04d65-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="04d65-132">ExceptionFlags</span></span>|<span data-ttu-id="04d65-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04d65-133">win:UInt16</span></span>|<span data-ttu-id="04d65-134">0x01: HasInnerException (Visual Basic のドキュメントで「[CLR ETW イベント](clr-etw-events.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="04d65-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="04d65-135">0x02: IsNestedException。</span><span class="sxs-lookup"><span data-stu-id="04d65-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="04d65-136">0x04: IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="04d65-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="04d65-137">0x08: IsCorruptedStateException (プロセスの状態が破損していることを示します。「[破損状態の例外の処理](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04d65-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="04d65-138">0x10: IsCLSCompliant (<xref:System.Exception> から派生した例外は CLS 準拠で、それ以外は CLS 非準拠)。</span><span class="sxs-lookup"><span data-stu-id="04d65-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="04d65-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="04d65-139">ClrInstanceID</span></span>|<span data-ttu-id="04d65-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04d65-140">win:UInt16</span></span>|<span data-ttu-id="04d65-141">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="04d65-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04d65-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="04d65-142">See also</span></span>

- [<span data-ttu-id="04d65-143">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="04d65-143">CLR ETW Events</span></span>](clr-etw-events.md)
