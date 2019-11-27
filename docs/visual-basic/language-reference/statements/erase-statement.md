---
title: Erase ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343700"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="ced5a-102">Erase ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ced5a-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="ced5a-103">配列変数を解放し、それらの要素に使用されるメモリの割り当てを解除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ced5a-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="ced5a-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="ced5a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ced5a-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="ced5a-106">必須。</span><span class="sxs-lookup"><span data-stu-id="ced5a-106">Required.</span></span> <span data-ttu-id="ced5a-107">消去する配列変数の一覧。</span><span class="sxs-lookup"><span data-stu-id="ced5a-107">List of array variables to be erased.</span></span> <span data-ttu-id="ced5a-108">複数の変数を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="ced5a-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ced5a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ced5a-109">Remarks</span></span>  
 <span data-ttu-id="ced5a-110">`Erase` ステートメントは、プロシージャレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ced5a-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="ced5a-111">これは、プロシージャ内では、クラスレベルまたはモジュールレベルではなく、配列を解放できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ced5a-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="ced5a-112">`Erase` ステートメントは、各配列変数に `Nothing` を割り当てることと同じです。</span><span class="sxs-lookup"><span data-stu-id="ced5a-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced5a-113">例</span><span class="sxs-lookup"><span data-stu-id="ced5a-113">Example</span></span>  
 <span data-ttu-id="ced5a-114">次の例では、`Erase` ステートメントを使用して2つの配列をクリアし、メモリ (それぞれ1000と100のストレージ要素) を解放します。</span><span class="sxs-lookup"><span data-stu-id="ced5a-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="ced5a-115">次に、`ReDim` ステートメントによって、3次元配列に新しい配列インスタンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ced5a-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="ced5a-116">参照</span><span class="sxs-lookup"><span data-stu-id="ced5a-116">See also</span></span>

- [<span data-ttu-id="ced5a-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="ced5a-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="ced5a-118">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="ced5a-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
