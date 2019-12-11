---
title: "'<eventname>' はイベントであるため、直接呼び出すことはできません。"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803323"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="601c4-102">'\<eventname >' はイベントであるため、直接呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="601c4-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="601c4-103">' <`eventname`>' は、イベントで、これは直接呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="601c4-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="601c4-104">使用して、`RaiseEvent`イベントを発生させるステートメントです。</span><span class="sxs-lookup"><span data-stu-id="601c4-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="601c4-105">プロシージャ呼び出しでは、イベント プロシージャ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="601c4-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="601c4-106">イベント ハンドラーは、プロシージャが、イベント自体はシグナル デバイスで発生して処理する必要がありますが、です。</span><span class="sxs-lookup"><span data-stu-id="601c4-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="601c4-107">**エラー ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="601c4-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="601c4-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="601c4-108">To correct this error</span></span>  
  
1. <span data-ttu-id="601c4-109">使用して、`RaiseEvent`イベントを通知し、それを処理する手順を起動するステートメント。</span><span class="sxs-lookup"><span data-stu-id="601c4-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="601c4-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="601c4-110">See also</span></span>

- [<span data-ttu-id="601c4-111">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="601c4-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
