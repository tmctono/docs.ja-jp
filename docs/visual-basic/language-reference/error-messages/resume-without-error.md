---
title: エラーが発生していないときに Resume を実行することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300906"
---
# <a name="resume-without-error"></a><span data-ttu-id="03f57-102">エラーが発生していないときに Resume を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="03f57-102">Resume without error</span></span>
<span data-ttu-id="03f57-103">A`Resume`ステートメントが外部のエラー処理コードを表示またはエラーがなかった場合でも、コードがエラー ハンドラーにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="03f57-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03f57-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="03f57-104">To correct this error</span></span>  
  
1. <span data-ttu-id="03f57-105">移動、`Resume`ステートメント エラー ハンドラーを削除したりします。</span><span class="sxs-lookup"><span data-stu-id="03f57-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="03f57-106">エラー ハンドラーを識別するラベルのプロシージャに、検索をラベルにジャンプは、プロシージャ間で発生することはできません。</span><span class="sxs-lookup"><span data-stu-id="03f57-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="03f57-107">対象として指定された重複するラベルを検索する場合、`GoTo`ステートメントではなく、`On Error GoTo`ステートメントでは、目的のターゲットと一致する行のラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="03f57-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f57-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="03f57-108">See also</span></span>

- [<span data-ttu-id="03f57-109">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="03f57-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="03f57-110">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="03f57-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
