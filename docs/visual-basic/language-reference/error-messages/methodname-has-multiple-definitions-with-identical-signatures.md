---
title: メソッド '<methodname>' には、同じシグネチャを持つ複数の定義が含まれています。
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: b884220053bbcec633c964a41892bc8df42f41c7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602437"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="881ac-102">'\<methodname>' には、同じシグネチャを持つ複数の定義が含まれています</span><span class="sxs-lookup"><span data-stu-id="881ac-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="881ac-103">`Function` または `Sub` プロシージャ宣言で、前の宣言と同じプロシージャ名と引数リストを使用しています。</span><span class="sxs-lookup"><span data-stu-id="881ac-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="881ac-104">考えられる原因の 1 つは、元のプロシージャをオーバーロードしようとしたことです。</span><span class="sxs-lookup"><span data-stu-id="881ac-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="881ac-105">オーバーロードされたプロシージャには、異なる引数リストが必要です。</span><span class="sxs-lookup"><span data-stu-id="881ac-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="881ac-106">**エラー ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="881ac-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="881ac-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="881ac-107">To correct this error</span></span>  
  
- <span data-ttu-id="881ac-108">プロシージャ名または引数リストを変更するか、または重複する宣言を削除します。</span><span class="sxs-lookup"><span data-stu-id="881ac-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881ac-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="881ac-109">See also</span></span>

- [<span data-ttu-id="881ac-110">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="881ac-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="881ac-111">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="881ac-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
