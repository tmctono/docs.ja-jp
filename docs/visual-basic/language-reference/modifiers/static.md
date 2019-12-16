---
title: Static
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350760"
---
# <a name="static-visual-basic"></a><span data-ttu-id="381af-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="381af-102">Static (Visual Basic)</span></span>
<span data-ttu-id="381af-103">1つ以上の宣言されたローカル変数が引き続き存在し、宣言されているプロシージャの終了後もその最新の値を保持することを指定します。</span><span class="sxs-lookup"><span data-stu-id="381af-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="381af-104">コメント</span><span class="sxs-lookup"><span data-stu-id="381af-104">Remarks</span></span>  
 <span data-ttu-id="381af-105">通常、プロシージャ内のローカル変数は、プロシージャが停止するとすぐに存在しなくなります。</span><span class="sxs-lookup"><span data-stu-id="381af-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="381af-106">静的変数は引き続き存在し、最新の値が保持されます。</span><span class="sxs-lookup"><span data-stu-id="381af-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="381af-107">次回コードがプロシージャを呼び出したとき、変数は再初期化されず、割り当てた最新の値も保持されます。</span><span class="sxs-lookup"><span data-stu-id="381af-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="381af-108">静的変数は、その変数が定義されているクラスまたはモジュールの有効期間にわたって存在し続けます。</span><span class="sxs-lookup"><span data-stu-id="381af-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="381af-109">ルール</span><span class="sxs-lookup"><span data-stu-id="381af-109">Rules</span></span>  
  
- <span data-ttu-id="381af-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="381af-110">**Declaration Context.**</span></span> <span data-ttu-id="381af-111">`Static` は、ローカル変数に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="381af-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="381af-112">つまり、`Static` 変数の宣言コンテキストはプロシージャ内のプロシージャまたはブロックである必要があり、ソースファイル、名前空間、クラス、構造体、またはモジュールにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="381af-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="381af-113">構造体プロシージャ内で `Static` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="381af-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="381af-114">`Static` ローカル変数のデータ型を推論できません。</span><span class="sxs-lookup"><span data-stu-id="381af-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="381af-115">詳細については、「[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381af-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="381af-116">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="381af-116">**Combined Modifiers.**</span></span> <span data-ttu-id="381af-117">同じ宣言内で `ReadOnly`、`Shadows`、または `Shared` と共に `Static` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="381af-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="381af-118">動作</span><span class="sxs-lookup"><span data-stu-id="381af-118">Behavior</span></span>  
 <span data-ttu-id="381af-119">`Shared` プロシージャで静的変数を宣言する場合、アプリケーション全体で使用できる静的変数のコピーは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="381af-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="381af-120">クラスのインスタンスを参照する変数ではなく、クラス名を使用して `Shared` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="381af-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="381af-121">`Shared`ていないプロシージャで静的変数を宣言した場合、クラスの各インスタンスに対して使用できる変数のコピーは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="381af-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="381af-122">非共有プロシージャを呼び出すには、クラスの特定のインスタンスを指す変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="381af-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="381af-123">例</span><span class="sxs-lookup"><span data-stu-id="381af-123">Example</span></span>  
 <span data-ttu-id="381af-124">次の例は、`Static` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="381af-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="381af-125">`Static` 変数 `totalSales` は、1回だけ0に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="381af-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="381af-126">`updateSales`を入力するたびに、`totalSales` に計算した最新の値がまだ含まれています。</span><span class="sxs-lookup"><span data-stu-id="381af-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="381af-127">このコンテキストでは、`Static` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="381af-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="381af-128">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="381af-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="381af-129">参照</span><span class="sxs-lookup"><span data-stu-id="381af-129">See also</span></span>

- [<span data-ttu-id="381af-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="381af-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="381af-131">Shared</span><span class="sxs-lookup"><span data-stu-id="381af-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="381af-132">Visual Basic の有効期間</span><span class="sxs-lookup"><span data-stu-id="381af-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="381af-133">変数宣言</span><span class="sxs-lookup"><span data-stu-id="381af-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="381af-134">構造体</span><span class="sxs-lookup"><span data-stu-id="381af-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="381af-135">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="381af-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="381af-136">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="381af-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
