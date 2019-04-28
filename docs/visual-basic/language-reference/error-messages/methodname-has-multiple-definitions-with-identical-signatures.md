---
title: メソッド '<methodname>' には、同じシグネチャを持つ複数の定義が含まれています。
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920901"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="cd0d5-102">'\<methodname >' が同じシグネチャを持つ複数の定義</span><span class="sxs-lookup"><span data-stu-id="cd0d5-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="cd0d5-103">`Function`または`Sub`プロシージャ宣言では、前の宣言と同じプロシージャの名前と引数のリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd0d5-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="cd0d5-104">1 つの考えられる原因は、元のプロシージャをオーバー ロードする試みです。</span><span class="sxs-lookup"><span data-stu-id="cd0d5-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="cd0d5-105">オーバー ロードされたプロシージャには、異なる引数リストが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd0d5-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="cd0d5-106">**エラー ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="cd0d5-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd0d5-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="cd0d5-107">To correct this error</span></span>  
  
- <span data-ttu-id="cd0d5-108">プロシージャ名か、引数リストを変更するか、重複の宣言を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd0d5-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0d5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd0d5-109">See also</span></span>

- [<span data-ttu-id="cd0d5-110">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="cd0d5-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cd0d5-111">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="cd0d5-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
