---
title: Exception Thrown_V1 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723018"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="0bb78-102">Exception Thrown_V1 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="0bb78-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="0bb78-103">このイベントは、スローされる例外に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="0bb78-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="0bb78-104">イベントが発生するキーワードとイベントのレベルを次の表に示します </span><span class="sxs-lookup"><span data-stu-id="0bb78-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="0bb78-105">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="0bb78-106">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0bb78-106">Keyword for raising the event</span></span>|<span data-ttu-id="0bb78-107">レベル</span><span class="sxs-lookup"><span data-stu-id="0bb78-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0bb78-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="0bb78-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="0bb78-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="0bb78-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="0bb78-110">次の表にイベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0bb78-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="0bb78-111">event</span><span class="sxs-lookup"><span data-stu-id="0bb78-111">Event</span></span>|<span data-ttu-id="0bb78-112">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0bb78-112">Event ID</span></span>|<span data-ttu-id="0bb78-113">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0bb78-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="0bb78-114">80</span><span class="sxs-lookup"><span data-stu-id="0bb78-114">80</span></span>|<span data-ttu-id="0bb78-115">マネージド例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0bb78-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="0bb78-116">次の表にイベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0bb78-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="0bb78-117">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0bb78-117">Field name</span></span>|<span data-ttu-id="0bb78-118">データ型</span><span class="sxs-lookup"><span data-stu-id="0bb78-118">Data type</span></span>|<span data-ttu-id="0bb78-119">説明</span><span class="sxs-lookup"><span data-stu-id="0bb78-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0bb78-120">例外の種類</span><span class="sxs-lookup"><span data-stu-id="0bb78-120">Exception Type</span></span>|<span data-ttu-id="0bb78-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0bb78-121">win:UnicodeString</span></span>|<span data-ttu-id="0bb78-122">例外の種類 (`System.NullReferenceException` など)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="0bb78-123">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="0bb78-123">Exception Message</span></span>|<span data-ttu-id="0bb78-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0bb78-124">win:UnicodeString</span></span>|<span data-ttu-id="0bb78-125">実際の例外メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0bb78-125">Actual exception message.</span></span>|  
|<span data-ttu-id="0bb78-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="0bb78-126">EIPCodeThrow</span></span>|<span data-ttu-id="0bb78-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="0bb78-127">win:Pointer</span></span>|<span data-ttu-id="0bb78-128">例外が発生した命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="0bb78-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="0bb78-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="0bb78-129">ExceptionHR</span></span>|<span data-ttu-id="0bb78-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0bb78-130">win:UInt32</span></span>|<span data-ttu-id="0bb78-131">例外 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="0bb78-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="0bb78-132">ExceptionFlags</span></span>|<span data-ttu-id="0bb78-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0bb78-133">win:UInt16</span></span>|<span data-ttu-id="0bb78-134">0x01:HasInnerException (を参照してください[CLR ETW イベント](../../../docs/framework/performance/clr-etw-events.md)Visual Basic のドキュメントで)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="0bb78-135">0x02:IsNestedException。</span><span class="sxs-lookup"><span data-stu-id="0bb78-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="0bb78-136">0x04:IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="0bb78-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="0bb78-137">0x08:IsCorruptedStateException (プロセスの状態が破損していることを示します。 表示[破損状態例外を処理](https://go.microsoft.com/fwlink/?LinkId=179681)msdn)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="0bb78-138">0x10:IsCLSCompliant (から派生した例外<xref:System.Exception>が CLS に準拠していません。 それ以外は CLS 準拠)。</span><span class="sxs-lookup"><span data-stu-id="0bb78-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="0bb78-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0bb78-139">ClrInstanceID</span></span>|<span data-ttu-id="0bb78-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0bb78-140">win:UInt16</span></span>|<span data-ttu-id="0bb78-141">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0bb78-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bb78-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bb78-142">See also</span></span>

- [<span data-ttu-id="0bb78-143">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="0bb78-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
