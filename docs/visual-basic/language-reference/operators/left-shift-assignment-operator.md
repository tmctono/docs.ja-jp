---
title: <<= 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350956"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ba9f8-102">\<\<= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba9f8-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="ba9f8-103">変数またはプロパティの値に対して算術左シフトを実行し、結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba9f8-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="ba9f8-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ba9f8-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ba9f8-106">必須。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-106">Required.</span></span> <span data-ttu-id="ba9f8-107">整数型の変数またはプロパティ (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="ba9f8-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-108">Required.</span></span> <span data-ttu-id="ba9f8-109">`Integer`に拡大変換されるデータ型の数値式。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba9f8-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ba9f8-110">Remarks</span></span>  
 <span data-ttu-id="ba9f8-111">`<<=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ba9f8-112">変数またはプロパティを [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ba9f8-113">`<<=` 演算子は、まず変数またはプロパティの値に対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="ba9f8-114">次に、演算子は、その操作の結果をその変数またはプロパティに戻します。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="ba9f8-115">算術シフトは循環していません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="ba9f8-116">算術左シフトでは、結果のデータ型の範囲を超えてシフトされたビットは破棄され、右側に空いているビット位置は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ba9f8-117">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="ba9f8-117">Overloading</span></span>  
 <span data-ttu-id="ba9f8-118">[< < 演算子](../../../visual-basic/language-reference/operators/left-shift-operator.md)は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ba9f8-119">`<<` 演算子のオーバーロードは、`<<=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="ba9f8-120">コードで `<<`をオーバーロードするクラスまたは構造体の `<<=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ba9f8-121">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9f8-122">例</span><span class="sxs-lookup"><span data-stu-id="ba9f8-122">Example</span></span>  
 <span data-ttu-id="ba9f8-123">次の例では、`<<=` 演算子を使用して、`Integer` 変数のビットパターンを指定された量だけ左にシフトし、その結果を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="ba9f8-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="ba9f8-124">参照</span><span class="sxs-lookup"><span data-stu-id="ba9f8-124">See also</span></span>

- [<span data-ttu-id="ba9f8-125"><< 演算子</span><span class="sxs-lookup"><span data-stu-id="ba9f8-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="ba9f8-126">代入演算子</span><span class="sxs-lookup"><span data-stu-id="ba9f8-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ba9f8-127">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="ba9f8-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="ba9f8-128">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="ba9f8-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ba9f8-129">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="ba9f8-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ba9f8-130">ステートメント</span><span class="sxs-lookup"><span data-stu-id="ba9f8-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
