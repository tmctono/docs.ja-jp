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
ms.openlocfilehash: ff7cbb02a9a10dbe11450491e93fd85fd77b44ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370662"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9150b-102">\<\<= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9150b-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="9150b-103">変数またはプロパティの値に算術左シフトを実行し、結果をその変数またはプロパティに戻して代入します。</span><span class="sxs-lookup"><span data-stu-id="9150b-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9150b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9150b-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="9150b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9150b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9150b-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="9150b-106">Required.</span></span> <span data-ttu-id="9150b-107">整数型の変数またはプロパティ (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="9150b-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="9150b-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="9150b-108">Required.</span></span> <span data-ttu-id="9150b-109">`Integer` に拡大されるデータ型の数値式。</span><span class="sxs-lookup"><span data-stu-id="9150b-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9150b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9150b-110">Remarks</span></span>  
 <span data-ttu-id="9150b-111">`<<=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9150b-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9150b-112">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9150b-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="9150b-113">`<<=` 演算子は、まず変数またはプロパティの値に対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9150b-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="9150b-114">次に、この演算子はその演算の結果をその変数またはプロパティに戻して代入します。</span><span class="sxs-lookup"><span data-stu-id="9150b-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="9150b-115">算術シフトは循環ではありません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="9150b-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="9150b-116">算術左シフトでは、結果のデータ型の範囲を超えてシフトされたビットは破棄され、右側に空いたビット位置は 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9150b-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9150b-117">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="9150b-117">Overloading</span></span>  
 <span data-ttu-id="9150b-118">[<< 演算子](left-shift-operator.md)は "*オーバーロード*" できます。つまり、オペランドがあるクラスまたは構造体の型を持っているときに、そのクラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="9150b-118">The [<< Operator](left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9150b-119">`<<` 演算子をオーバーロードすると、`<<=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="9150b-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="9150b-120">コードで、`<<` をオーバーロードするクラスまたは構造体で `<<=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9150b-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9150b-121">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9150b-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9150b-122">例</span><span class="sxs-lookup"><span data-stu-id="9150b-122">Example</span></span>  
 <span data-ttu-id="9150b-123">次の例では、`<<=` 演算子を使用して、`Integer` 変数のビット パターンを、指定された桁数だけ左にシフトし、結果をその変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="9150b-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="9150b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9150b-124">See also</span></span>

- [<span data-ttu-id="9150b-125"><< 演算子</span><span class="sxs-lookup"><span data-stu-id="9150b-125"><< Operator</span></span>](left-shift-operator.md)
- [<span data-ttu-id="9150b-126">代入演算子</span><span class="sxs-lookup"><span data-stu-id="9150b-126">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="9150b-127">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="9150b-127">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="9150b-128">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="9150b-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9150b-129">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="9150b-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="9150b-130">ステートメント</span><span class="sxs-lookup"><span data-stu-id="9150b-130">Statements</span></span>](../../programming-guide/language-features/statements.md)
