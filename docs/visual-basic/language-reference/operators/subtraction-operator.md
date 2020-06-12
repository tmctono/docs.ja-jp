---
title: '- 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 6539beb5cf8078281357445e2391fac189208087
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406355"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="fa7fb-102">- 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa7fb-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="fa7fb-103">2 つの数値式の差、またはある数値式の負の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa7fb-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="fa7fb-105">or</span><span class="sxs-lookup"><span data-stu-id="fa7fb-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="fa7fb-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="fa7fb-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="fa7fb-107">必須です。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-107">Required.</span></span> <span data-ttu-id="fa7fb-108">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="fa7fb-109">`–` 演算子で負の値を求める場合を除き、必須です。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="fa7fb-110">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="fa7fb-111">結果</span><span class="sxs-lookup"><span data-stu-id="fa7fb-111">Result</span></span>  
 <span data-ttu-id="fa7fb-112">結果は、`expression1` と `expression2` の差、または `expression1` の符号を反転した値になります。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="fa7fb-113">結果のデータ型は `expression1` および `expression2` のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="fa7fb-114">「[演算子の結果のデータ型](data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="fa7fb-115">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="fa7fb-115">Supported Types</span></span>  
 <span data-ttu-id="fa7fb-116">すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-116">All numeric types.</span></span> <span data-ttu-id="fa7fb-117">これには、符号なしおよび浮動小数点の型と `Decimal` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa7fb-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa7fb-118">Remarks</span></span>  
 <span data-ttu-id="fa7fb-119">前述の構文で示した最初の使用法では、`–` 演算子は、2 つの数値式の差を求める "*バイナリ*" 算術減算演算子です。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="fa7fb-120">前述の構文で示した 2 番目の使用法では、`–` 演算子は、式の負の値に対する "*単項*" 否定演算子です。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="fa7fb-121">この意味では、否定は、`expression1` が負の場合に結果が正になるように、`expression1` の符号を反転させることです。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="fa7fb-122">いずれかの式が [Nothing](../nothing.md) と評価される場合、`–` 演算子はそれを 0 として扱います。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-122">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa7fb-123">`–` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、このクラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fa7fb-124">コードで、そのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="fa7fb-125">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-125">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7fb-126">例</span><span class="sxs-lookup"><span data-stu-id="fa7fb-126">Example</span></span>  
 <span data-ttu-id="fa7fb-127">次の例では、`–` 演算子を使用して、2 つの数値の差を計算して返します。次に、数値の符号を反転させます。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="fa7fb-128">これらのステートメントの実行後、`binaryResult` には124.45 が格納委され、`unaryResult` には –334.90 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fa7fb-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7fb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa7fb-129">See also</span></span>

- [<span data-ttu-id="fa7fb-130">-= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa7fb-130">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="fa7fb-131">算術演算子</span><span class="sxs-lookup"><span data-stu-id="fa7fb-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="fa7fb-132">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="fa7fb-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="fa7fb-133">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="fa7fb-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="fa7fb-134">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="fa7fb-134">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
