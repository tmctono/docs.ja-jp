---
title: Erase ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638195"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="6afe2-102">Erase ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6afe2-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="6afe2-103">配列変数を解放し、その要素に使用されるメモリの割り当てを解除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6afe2-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6afe2-104">構文</span><span class="sxs-lookup"><span data-stu-id="6afe2-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="6afe2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6afe2-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="6afe2-106">必須。</span><span class="sxs-lookup"><span data-stu-id="6afe2-106">Required.</span></span> <span data-ttu-id="6afe2-107">消去する配列変数の一覧。</span><span class="sxs-lookup"><span data-stu-id="6afe2-107">List of array variables to be erased.</span></span> <span data-ttu-id="6afe2-108">複数の変数を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="6afe2-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6afe2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6afe2-109">Remarks</span></span>  
 <span data-ttu-id="6afe2-110">`Erase`ステートメントは、プロシージャ レベルでのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="6afe2-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="6afe2-111">これは、クラスまたはモジュール レベルではなく、プロシージャ内部では配列を解放することを意味します。</span><span class="sxs-lookup"><span data-stu-id="6afe2-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="6afe2-112">`Erase`ステートメントは割り当てることと同じ`Nothing`各配列変数にします。</span><span class="sxs-lookup"><span data-stu-id="6afe2-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6afe2-113">例</span><span class="sxs-lookup"><span data-stu-id="6afe2-113">Example</span></span>  
 <span data-ttu-id="6afe2-114">次の例では、`Erase`を 2 つの配列をクリアし、そのメモリを解放ステートメント (1,000 と 100 のストレージ要素それぞれ)。</span><span class="sxs-lookup"><span data-stu-id="6afe2-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="6afe2-115">`ReDim`ステートメントし、配列の新しいインスタンスを 3 次元の配列に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6afe2-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="6afe2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6afe2-116">See also</span></span>

- [<span data-ttu-id="6afe2-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="6afe2-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="6afe2-118">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="6afe2-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
