---
title: TypeOf 演算子
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406328"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="4cd9b-102">TypeOf 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cd9b-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="4cd9b-103">式の結果の実行時の型に、指定された型との型互換性があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-103">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4cd9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cd9b-104">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="4cd9b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="4cd9b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4cd9b-106">必須。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-106">Returned.</span></span> <span data-ttu-id="4cd9b-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="4cd9b-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-108">Required.</span></span> <span data-ttu-id="4cd9b-109">参照型に評価される任意の式。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="4cd9b-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-110">Required.</span></span> <span data-ttu-id="4cd9b-111">任意のデータ型名。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cd9b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="4cd9b-112">Remarks</span></span>  
 <span data-ttu-id="4cd9b-113">`TypeOf` 演算子は、`objectexpression` の実行時の型が `typename` と互換性があるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="4cd9b-114">互換性は、`typename` の型のカテゴリに依存します。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="4cd9b-115">互換性を決定する方法を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="4cd9b-116">`typename` の型のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="4cd9b-116">Type category of `typename`</span></span>|<span data-ttu-id="4cd9b-117">互換性の条件</span><span class="sxs-lookup"><span data-stu-id="4cd9b-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="4cd9b-118">クラス</span><span class="sxs-lookup"><span data-stu-id="4cd9b-118">Class</span></span>|<span data-ttu-id="4cd9b-119">`objectexpression` が `typename` 型である、または `typename` を継承する</span><span class="sxs-lookup"><span data-stu-id="4cd9b-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="4cd9b-120">構造体</span><span class="sxs-lookup"><span data-stu-id="4cd9b-120">Structure</span></span>|<span data-ttu-id="4cd9b-121">`objectexpression` が `typename` 型である</span><span class="sxs-lookup"><span data-stu-id="4cd9b-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="4cd9b-122">Interface</span><span class="sxs-lookup"><span data-stu-id="4cd9b-122">Interface</span></span>|<span data-ttu-id="4cd9b-123">`objectexpression` が `typename` を実装する、または `typename` を実装するクラスを継承する</span><span class="sxs-lookup"><span data-stu-id="4cd9b-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="4cd9b-124">`objectexpression` の実行時の型が互換性の条件を満たす場合、`result` は `True` です。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="4cd9b-125">それ以外の場合、`result` は `False` です。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="4cd9b-126">`objectexpression` が null の場合、`TypeOf`...`Is` は `False` を返し、...`IsNot` は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="4cd9b-127">`TypeOf` は、常に `Is` キーワードと共に `TypeOf`...`Is` 式を構築するか、または `IsNot` キーワードと共に `TypeOf`...`IsNot` 式を構築します。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cd9b-128">例</span><span class="sxs-lookup"><span data-stu-id="4cd9b-128">Example</span></span>  
 <span data-ttu-id="4cd9b-129">次の例では、`TypeOf`...`Is` 式でさまざまなデータ型を使用して、2 つのオブジェクト参照変数の型の互換性をテストしています。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="4cd9b-130">変数 `refInteger` は、実行時の型 `Integer` を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="4cd9b-131">`Integer` と互換性がありますが、`Double` との互換性はありません。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="4cd9b-132">変数 `refForm` は、実行時の型 <xref:System.Windows.Forms.Form> を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="4cd9b-133">この変数は、<xref:System.Windows.Forms.Form> (同じ型)、<xref:System.Windows.Forms.Control> (<xref:System.Windows.Forms.Form> は <xref:System.Windows.Forms.Control> を継承する)、および <xref:System.ComponentModel.IComponent> (<xref:System.Windows.Forms.Form> は <xref:System.ComponentModel.IComponent> を実装する <xref:System.ComponentModel.Component> を継承する) と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="4cd9b-134">ただし、`refForm` には <xref:System.Windows.Forms.Label> との互換性はありません。</span><span class="sxs-lookup"><span data-stu-id="4cd9b-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd9b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cd9b-135">See also</span></span>

- [<span data-ttu-id="4cd9b-136">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="4cd9b-136">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="4cd9b-137">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="4cd9b-137">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="4cd9b-138">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="4cd9b-138">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="4cd9b-139">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="4cd9b-139">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="4cd9b-140">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="4cd9b-140">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="4cd9b-141">演算子および式</span><span class="sxs-lookup"><span data-stu-id="4cd9b-141">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
