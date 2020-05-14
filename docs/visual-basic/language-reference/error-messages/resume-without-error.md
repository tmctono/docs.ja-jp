---
title: エラーが発生していないときに Resume を実行することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055161"
---
# <a name="resume-without-error"></a><span data-ttu-id="1dfac-102">エラーが発生していないときに Resume を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1dfac-102">Resume without error</span></span>
<span data-ttu-id="1dfac-103">`Resume` ステートメントがエラー処理コードの外側に記述されていたか、エラーが発生していない場合でもコードがエラー ハンドラーにジャンプしました。</span><span class="sxs-lookup"><span data-stu-id="1dfac-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1dfac-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1dfac-104">To correct this error</span></span>  
  
1. <span data-ttu-id="1dfac-105">`Resume` ステートメントをエラー ハンドラー内に移動するか、または削除します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="1dfac-106">プロシージャ間でラベルにジャンプすることはできないため、プロシージャでエラー ハンドラーを識別するラベルを検索します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="1dfac-107">`On Error GoTo` ステートメントではない `GoTo` ステートメントのターゲットとして重複するラベルが指定されている場合は、その目的のターゲットと一致するように行ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="1dfac-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfac-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dfac-108">See also</span></span>

- [<span data-ttu-id="1dfac-109">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="1dfac-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="1dfac-110">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="1dfac-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
