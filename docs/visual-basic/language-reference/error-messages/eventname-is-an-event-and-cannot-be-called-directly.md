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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803323"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="5339b-102">'\<eventname>' はイベントであるため、直接呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="5339b-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="5339b-103">'<`eventname`>' はイベントであるため、直接呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5339b-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="5339b-104">`RaiseEvent` ステートメントを使用して、イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="5339b-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="5339b-105">プロシージャ呼び出しは、プロシージャ名のイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5339b-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="5339b-106">イベント ハンドラーはプロシージャですが、イベント自体はシグナル通知デバイスであり、これを発生させて処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5339b-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="5339b-107">**エラー ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="5339b-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5339b-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5339b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="5339b-109">`RaiseEvent` ステートメントを使用して、イベントを通知し、それを処理するプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5339b-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5339b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5339b-110">See also</span></span>

- [<span data-ttu-id="5339b-111">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="5339b-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
