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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343700"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="f9639-102">Erase ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9639-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="f9639-103">配列変数を解放し、それらの要素に使用されるメモリの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="f9639-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9639-104">構文</span><span class="sxs-lookup"><span data-stu-id="f9639-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="f9639-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f9639-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="f9639-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="f9639-106">Required.</span></span> <span data-ttu-id="f9639-107">消去する配列変数の一覧。</span><span class="sxs-lookup"><span data-stu-id="f9639-107">List of array variables to be erased.</span></span> <span data-ttu-id="f9639-108">複数の変数を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f9639-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9639-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9639-109">Remarks</span></span>  
 <span data-ttu-id="f9639-110">`Erase` ステートメントは、プロシージャ レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9639-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="f9639-111">つまり、プロシージャ内では配列を解放できますが、クラスまたはモジュール レベルでは解放できません。</span><span class="sxs-lookup"><span data-stu-id="f9639-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="f9639-112">`Erase` ステートメントは、各配列変数に `Nothing` を割り当てることと同じです。</span><span class="sxs-lookup"><span data-stu-id="f9639-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9639-113">例</span><span class="sxs-lookup"><span data-stu-id="f9639-113">Example</span></span>  
 <span data-ttu-id="f9639-114">次の例では、`Erase` ステートメントを使用して 2 つの配列をクリアし、そのメモリを解放します (それぞれ 1000 および 100 ストレージ要素)。</span><span class="sxs-lookup"><span data-stu-id="f9639-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="f9639-115">次に、`ReDim` ステートメントを使用して、新しい配列インスタンスを 3 次元配列に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f9639-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="f9639-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9639-116">See also</span></span>

- [<span data-ttu-id="f9639-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="f9639-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="f9639-118">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f9639-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
