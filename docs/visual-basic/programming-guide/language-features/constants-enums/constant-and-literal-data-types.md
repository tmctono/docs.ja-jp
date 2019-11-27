---
title: 定数とリテラルのデータ型
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333725"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="4b161-102">定数とリテラルのデータ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b161-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="4b161-103">リテラルは、変数の値または式の結果 (数値3や文字列 "Hello" など) としてではなく、単独で表現される値です。</span><span class="sxs-lookup"><span data-stu-id="4b161-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="4b161-104">定数は、リテラルの代わりとなる意味のある名前で、値が変更される可能性がある変数とは対照的に、プログラム全体で同じ値を保持します。</span><span class="sxs-lookup"><span data-stu-id="4b161-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="4b161-105">[オプションの推論](../../../../visual-basic/language-reference/statements/option-infer-statement.md)が `Off`、 [option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)が `On`場合、データ型を使用してすべての定数を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b161-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="4b161-106">次の例では、`MyByte` のデータ型がデータ型 `Byte`として明示的に宣言されています。</span><span class="sxs-lookup"><span data-stu-id="4b161-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="4b161-107">`Option Infer` が `On` または `Option Strict` が `Off`場合は、`As` 句を使用してデータ型を指定せずに定数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4b161-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="4b161-108">コンパイラは、式の型から定数の型を特定します。</span><span class="sxs-lookup"><span data-stu-id="4b161-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="4b161-109">数値整数リテラルは、既定で `Integer` データ型にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="4b161-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="4b161-110">浮動小数点数の既定のデータ型は `Double`であり、キーワード `True` と `False` は `Boolean` 定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b161-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="4b161-111">リテラルと型の強制変換</span><span class="sxs-lookup"><span data-stu-id="4b161-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="4b161-112">場合によっては、リテラルを特定のデータ型に強制的に適用することが必要になることがあります。たとえば、`Decimal`型の変数に特に大きな整数リテラル値を割り当てる場合などです。</span><span class="sxs-lookup"><span data-stu-id="4b161-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="4b161-113">次の例では、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4b161-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="4b161-114">このエラーは、リテラルの表現によって発生します。</span><span class="sxs-lookup"><span data-stu-id="4b161-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="4b161-115">`Decimal` のデータ型はこの値を大きく保持できますが、リテラルは暗黙的に `Long`として表されます。これはできません。</span><span class="sxs-lookup"><span data-stu-id="4b161-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="4b161-116">リテラルを特定のデータ型に強制的に変換するには、型文字を追加する方法と、それを囲む文字内に配置する方法の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4b161-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="4b161-117">型文字または囲み文字は、リテラルの前または後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b161-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="4b161-118">前の例を機能させるには、リテラルに `D` 型文字を追加して、それを `Decimal`として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="4b161-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="4b161-119">次の例は、型文字と囲み文字の正しい使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b161-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="4b161-120">次の表は、Visual Basic で使用できる囲み文字と型文字を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b161-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="4b161-121">データ型</span><span class="sxs-lookup"><span data-stu-id="4b161-121">Data type</span></span>|<span data-ttu-id="4b161-122">囲み文字</span><span class="sxs-lookup"><span data-stu-id="4b161-122">Enclosing character</span></span>|<span data-ttu-id="4b161-123">追加された型文字</span><span class="sxs-lookup"><span data-stu-id="4b161-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="4b161-124">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-124">(none)</span></span>|<span data-ttu-id="4b161-125">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="4b161-126">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-126">(none)</span></span>|<span data-ttu-id="4b161-127">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="4b161-128">"</span><span class="sxs-lookup"><span data-stu-id="4b161-128">"</span></span>|<span data-ttu-id="4b161-129">C</span><span class="sxs-lookup"><span data-stu-id="4b161-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="4b161-130">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="4b161-131">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-131">(none)</span></span>|<span data-ttu-id="4b161-132">D または@</span><span class="sxs-lookup"><span data-stu-id="4b161-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="4b161-133">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-133">(none)</span></span>|<span data-ttu-id="4b161-134">R または#</span><span class="sxs-lookup"><span data-stu-id="4b161-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="4b161-135">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-135">(none)</span></span>|<span data-ttu-id="4b161-136">I または%</span><span class="sxs-lookup"><span data-stu-id="4b161-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="4b161-137">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-137">(none)</span></span>|<span data-ttu-id="4b161-138">L または &</span><span class="sxs-lookup"><span data-stu-id="4b161-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="4b161-139">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-139">(none)</span></span>|<span data-ttu-id="4b161-140">S</span><span class="sxs-lookup"><span data-stu-id="4b161-140">S</span></span>|  
|`Single`|<span data-ttu-id="4b161-141">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-141">(none)</span></span>|<span data-ttu-id="4b161-142">F または!</span><span class="sxs-lookup"><span data-stu-id="4b161-142">F or !</span></span>|  
|`String`|<span data-ttu-id="4b161-143">"</span><span class="sxs-lookup"><span data-stu-id="4b161-143">"</span></span>|<span data-ttu-id="4b161-144">(なし)</span><span class="sxs-lookup"><span data-stu-id="4b161-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b161-145">参照</span><span class="sxs-lookup"><span data-stu-id="4b161-145">See also</span></span>

- [<span data-ttu-id="4b161-146">ユーザー定義定数</span><span class="sxs-lookup"><span data-stu-id="4b161-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="4b161-147">方法 : 定数を宣言する</span><span class="sxs-lookup"><span data-stu-id="4b161-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="4b161-148">定数の概要</span><span class="sxs-lookup"><span data-stu-id="4b161-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="4b161-149">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="4b161-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4b161-150">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="4b161-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="4b161-151">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="4b161-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="4b161-152">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="4b161-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="4b161-153">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="4b161-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="4b161-154">データの種類</span><span class="sxs-lookup"><span data-stu-id="4b161-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4b161-155">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="4b161-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
