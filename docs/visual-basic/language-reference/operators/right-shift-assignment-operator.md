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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351993"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="702ec-102">>>= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="702ec-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="702ec-103">変数またはプロパティの値に算術右シフトを実行し、結果をその変数またはプロパティに戻して代入します。</span><span class="sxs-lookup"><span data-stu-id="702ec-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="702ec-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="702ec-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="702ec-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="702ec-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="702ec-106">Required.</span></span> <span data-ttu-id="702ec-107">整数型の変数またはプロパティ (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="702ec-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="702ec-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="702ec-108">Required.</span></span> <span data-ttu-id="702ec-109">`Integer` に拡大されるデータ型の数値式。</span><span class="sxs-lookup"><span data-stu-id="702ec-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="702ec-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="702ec-110">Remarks</span></span>  
 <span data-ttu-id="702ec-111">`>>=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="702ec-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="702ec-112">変数またはプロパティを [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="702ec-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="702ec-113">`>>=` 演算子は、まず変数またはプロパティの値に対して算術右シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="702ec-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="702ec-114">次に、この演算子はその演算の結果を変数またはプロパティに戻して代入します。</span><span class="sxs-lookup"><span data-stu-id="702ec-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="702ec-115">算術シフトは循環ではありません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="702ec-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="702ec-116">算術右シフトでは、右端のビット位置を超えてシフトされたビットは破棄され、左端ビットは左側の空いたビット位置に移されます。</span><span class="sxs-lookup"><span data-stu-id="702ec-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="702ec-117">したがって、`variableorproperty` に負の値がある場合、空いている位置は 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="702ec-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="702ec-118">`variableorproperty` が正の場合、またはそのデータ型が符号なしの型の場合、空いている位置は 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="702ec-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="702ec-119">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="702ec-119">Overloading</span></span>  
 <span data-ttu-id="702ec-120">[>> 演算子](../../../visual-basic/language-reference/operators/right-shift-operator.md)は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="702ec-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="702ec-121">`>>` 演算子をオーバーロードすると、`>>=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="702ec-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="702ec-122">コードで、`>>` をオーバーロードするクラスまたは構造体に `>>=` を使用する場合は、再定義された動作を確実に理解するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="702ec-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="702ec-123">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="702ec-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="702ec-124">例</span><span class="sxs-lookup"><span data-stu-id="702ec-124">Example</span></span>  
 <span data-ttu-id="702ec-125">次の例では、`>>=` 演算子を使用して、`Integer` 変数のビット パターンを、指定された桁数だけ右にシフトし、結果をその変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="702ec-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="702ec-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="702ec-126">See also</span></span>

- [<span data-ttu-id="702ec-127">>> 演算子</span><span class="sxs-lookup"><span data-stu-id="702ec-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="702ec-128">代入演算子</span><span class="sxs-lookup"><span data-stu-id="702ec-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="702ec-129">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="702ec-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="702ec-130">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="702ec-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="702ec-131">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="702ec-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="702ec-132">ステートメント</span><span class="sxs-lookup"><span data-stu-id="702ec-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
