---
title: Exception Thrown_V1 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91abd9e6f31380b7e8cd3df1a14aa5c5722901ba
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046511"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="c4598-102">Exception Thrown_V1 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c4598-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="c4598-103">このイベントは、スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c4598-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="c4598-104">イベントが発生するキーワードとイベントのレベルを次の表に示します</span><span class="sxs-lookup"><span data-stu-id="c4598-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="c4598-105">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c4598-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c4598-106">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c4598-106">Keyword for raising the event</span></span>|<span data-ttu-id="c4598-107">レベル</span><span class="sxs-lookup"><span data-stu-id="c4598-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c4598-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="c4598-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="c4598-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="c4598-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="c4598-110">次の表にイベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c4598-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="c4598-111">イベント</span><span class="sxs-lookup"><span data-stu-id="c4598-111">Event</span></span>|<span data-ttu-id="c4598-112">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c4598-112">Event ID</span></span>|<span data-ttu-id="c4598-113">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c4598-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="c4598-114">80</span><span class="sxs-lookup"><span data-stu-id="c4598-114">80</span></span>|<span data-ttu-id="c4598-115">マネージド例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c4598-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="c4598-116">次の表にイベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c4598-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="c4598-117">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c4598-117">Field name</span></span>|<span data-ttu-id="c4598-118">データ型</span><span class="sxs-lookup"><span data-stu-id="c4598-118">Data type</span></span>|<span data-ttu-id="c4598-119">説明</span><span class="sxs-lookup"><span data-stu-id="c4598-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c4598-120">例外の種類</span><span class="sxs-lookup"><span data-stu-id="c4598-120">Exception Type</span></span>|<span data-ttu-id="c4598-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c4598-121">win:UnicodeString</span></span>|<span data-ttu-id="c4598-122">例外の種類 (`System.NullReferenceException` など)。</span><span class="sxs-lookup"><span data-stu-id="c4598-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="c4598-123">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="c4598-123">Exception Message</span></span>|<span data-ttu-id="c4598-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c4598-124">win:UnicodeString</span></span>|<span data-ttu-id="c4598-125">実際の例外メッセージ。</span><span class="sxs-lookup"><span data-stu-id="c4598-125">Actual exception message.</span></span>|  
|<span data-ttu-id="c4598-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="c4598-126">EIPCodeThrow</span></span>|<span data-ttu-id="c4598-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c4598-127">win:Pointer</span></span>|<span data-ttu-id="c4598-128">例外が発生した命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="c4598-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="c4598-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="c4598-129">ExceptionHR</span></span>|<span data-ttu-id="c4598-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c4598-130">win:UInt32</span></span>|<span data-ttu-id="c4598-131">例外 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)。</span><span class="sxs-lookup"><span data-stu-id="c4598-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="c4598-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="c4598-132">ExceptionFlags</span></span>|<span data-ttu-id="c4598-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c4598-133">win:UInt16</span></span>|<span data-ttu-id="c4598-134">0x01HasInnerException (Visual Basic ドキュメントの「 [CLR ETW イベント](clr-etw-events.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c4598-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="c4598-135">除くIsNestedException.</span><span class="sxs-lookup"><span data-stu-id="c4598-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="c4598-136">0x04IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="c4598-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="c4598-137">0x08IsCorruptedStateException (プロセスの状態が破損していることを示します。「MSDN で[破損状態の例外を処理](https://go.microsoft.com/fwlink/?LinkId=179681)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c4598-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="c4598-138">0x10IsCLSCompliant (から<xref:System.Exception>派生する例外は cls に準拠していますが、それ以外の場合は cls に準拠していません)。</span><span class="sxs-lookup"><span data-stu-id="c4598-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="c4598-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c4598-139">ClrInstanceID</span></span>|<span data-ttu-id="c4598-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c4598-140">win:UInt16</span></span>|<span data-ttu-id="c4598-141">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c4598-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4598-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4598-142">See also</span></span>

- [<span data-ttu-id="c4598-143">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c4598-143">CLR ETW Events</span></span>](clr-etw-events.md)
