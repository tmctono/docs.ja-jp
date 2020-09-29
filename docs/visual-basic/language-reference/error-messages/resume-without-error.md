---
title: エラーが発生していないときに Resume を実行することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870828"
---
# <a name="resume-without-error"></a><span data-ttu-id="d54dd-102">エラーが発生していないときに Resume を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="d54dd-102">Resume without error</span></span>

<span data-ttu-id="d54dd-103">`Resume` ステートメントがエラー処理コードの外側に記述されていたか、エラーが発生していない場合でもコードがエラー ハンドラーにジャンプしました。</span><span class="sxs-lookup"><span data-stu-id="d54dd-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d54dd-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d54dd-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d54dd-105">`Resume` ステートメントをエラー ハンドラー内に移動するか、または削除します。</span><span class="sxs-lookup"><span data-stu-id="d54dd-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="d54dd-106">プロシージャ間でラベルにジャンプすることはできないため、プロシージャでエラー ハンドラーを識別するラベルを検索します。</span><span class="sxs-lookup"><span data-stu-id="d54dd-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="d54dd-107">`On Error GoTo` ステートメントではない `GoTo` ステートメントのターゲットとして重複するラベルが指定されている場合は、その目的のターゲットと一致するように行ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="d54dd-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54dd-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d54dd-108">See also</span></span>

- [<span data-ttu-id="d54dd-109">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="d54dd-109">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="d54dd-110">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="d54dd-110">On Error Statement</span></span>](../statements/on-error-statement.md)
