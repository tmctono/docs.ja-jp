---
title: '>>= 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: cad021c7730782d6233c60841483df7173308dc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351993"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="75393-102">> > = 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75393-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="75393-103">変数またはプロパティの値に対して算術右シフトを実行し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="75393-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75393-104">構文</span><span class="sxs-lookup"><span data-stu-id="75393-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="75393-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="75393-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="75393-106">必須。</span><span class="sxs-lookup"><span data-stu-id="75393-106">Required.</span></span> <span data-ttu-id="75393-107">整数型の変数またはプロパティ (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="75393-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="75393-108">必須。</span><span class="sxs-lookup"><span data-stu-id="75393-108">Required.</span></span> <span data-ttu-id="75393-109">`Integer`に拡大変換されるデータ型の数値式。</span><span class="sxs-lookup"><span data-stu-id="75393-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75393-110">コメント</span><span class="sxs-lookup"><span data-stu-id="75393-110">Remarks</span></span>  
 <span data-ttu-id="75393-111">`>>=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="75393-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="75393-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="75393-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="75393-113">`>>=` 演算子は、まず変数またはプロパティの値に対して算術右シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="75393-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="75393-114">次に、演算子は、その操作の結果を変数またはプロパティに戻します。</span><span class="sxs-lookup"><span data-stu-id="75393-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="75393-115">算術シフトは循環していません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="75393-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="75393-116">算術右シフトでは、右端のビット位置を超えてシフトされたビットは破棄され、左端のビットは左側に空いているビット位置に反映されます。</span><span class="sxs-lookup"><span data-stu-id="75393-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="75393-117">これは、`variableorproperty` に負の値がある場合、空いている位置が1に設定されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="75393-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="75393-118">`variableorproperty` が正の場合、またはそのデータ型が符号なしの型の場合、空いた位置は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="75393-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="75393-119">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="75393-119">Overloading</span></span>  
 <span data-ttu-id="75393-120">[> > 演算子](../../../visual-basic/language-reference/operators/right-shift-operator.md)は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="75393-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="75393-121">`>>` 演算子のオーバーロードは、`>>=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="75393-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="75393-122">コードで `>>`をオーバーロードするクラスまたは構造体の `>>=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="75393-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="75393-123">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75393-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75393-124">例</span><span class="sxs-lookup"><span data-stu-id="75393-124">Example</span></span>  
 <span data-ttu-id="75393-125">次の例では、`>>=` 演算子を使用して、`Integer` 変数のビットパターンを指定した量だけ右にシフトし、その結果を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="75393-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="75393-126">参照</span><span class="sxs-lookup"><span data-stu-id="75393-126">See also</span></span>

- [<span data-ttu-id="75393-127">>> 演算子</span><span class="sxs-lookup"><span data-stu-id="75393-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="75393-128">代入演算子</span><span class="sxs-lookup"><span data-stu-id="75393-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="75393-129">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="75393-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="75393-130">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="75393-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="75393-131">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="75393-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="75393-132">ステートメント</span><span class="sxs-lookup"><span data-stu-id="75393-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
