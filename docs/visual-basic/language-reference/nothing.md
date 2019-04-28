---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 97c651dbcc657fbab0706c9a959bd0031c0fe343
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778626"
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="e6e89-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6e89-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="e6e89-103">任意のデータ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-103">Represents the default value of any data type.</span></span> <span data-ttu-id="e6e89-104">参照型の場合、既定値は、`null`参照。</span><span class="sxs-lookup"><span data-stu-id="e6e89-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="e6e89-105">値の型の場合、既定値は、値の型が null 許容かどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6e89-106">Null 非許容値型の場合は、 `Nothing` Visual Basic では異なります`null`でC#します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="e6e89-107">Null 非許容値型の変数を設定した場合、Visual Basic で`Nothing`変数が宣言された型の既定値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e6e89-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="e6e89-108">C#を null 非許容値型の変数を割り当てる場合は、 `null`、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6e89-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6e89-109">Remarks</span></span>  
 <span data-ttu-id="e6e89-110">`Nothing` データ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="e6e89-111">既定値は、変数が、値の型または参照型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e6e89-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="e6e89-112">変数を*値の型*直接その値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6e89-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="e6e89-113">値の型は、すべての数値データ型を含める`Boolean`、 `Char`、 `Date`、すべての構造、およびすべての列挙体。</span><span class="sxs-lookup"><span data-stu-id="e6e89-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="e6e89-114">変数を*参照型*メモリ内オブジェクトのインスタンスへの参照を格納します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="e6e89-115">参照型には、クラス、配列、デリゲート、および文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6e89-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="e6e89-116">詳細については、「 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6e89-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="e6e89-117">変数は、値の場合は入力の動作`Nothing`かどうか、変数が null 許容のデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e6e89-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="e6e89-118">Null 許容値型を表す、追加、`?`修飾子を型名。</span><span class="sxs-lookup"><span data-stu-id="e6e89-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="e6e89-119">割り当てる`Nothing`null 許容型の変数に値を設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="e6e89-120">詳細と例については、次を参照してください。 [null 許容値型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="e6e89-121">変数が null 許容型でない値型の場合は、割り当てる`Nothing`に設定が既定値にその宣言された型。</span><span class="sxs-lookup"><span data-stu-id="e6e89-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="e6e89-122">その型に変数のメンバーが含まれている場合はすべて既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="e6e89-123">次の例は、スカラー型の場合、これを示しています。</span><span class="sxs-lookup"><span data-stu-id="e6e89-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 <span data-ttu-id="e6e89-124">変数が参照型の場合は、割り当てる`Nothing`変数設定、`null`変数の型の参照。</span><span class="sxs-lookup"><span data-stu-id="e6e89-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="e6e89-125">設定されている変数、`null`参照は任意のオブジェクトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="e6e89-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="e6e89-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 <span data-ttu-id="e6e89-127">変数は参照 (または null 許容値の型) かどうかをチェックするときに`null`、使用しない`= Nothing`または`<> Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="e6e89-128">常に使用する`Is Nothing`または`IsNot Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="e6e89-129">Visual Basic で文字列の場合、空の文字列に等しい`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="e6e89-130">そのため、`"" = Nothing`は true。</span><span class="sxs-lookup"><span data-stu-id="e6e89-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="e6e89-131">次の例を使用する比較を示しています、`Is`と`IsNot`演算子。</span><span class="sxs-lookup"><span data-stu-id="e6e89-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 <span data-ttu-id="e6e89-132">使用せずに変数を宣言する場合、`As`句に設定し、 `Nothing`、変数の型を持つ`Object`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="e6e89-133">この例は`Dim something = Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="e6e89-134">ここでは、コンパイル時エラーにとき`Option Strict`上と`Option Infer`はオフです。</span><span class="sxs-lookup"><span data-stu-id="e6e89-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="e6e89-135">割り当てるとき`Nothing`オブジェクト変数を参照しなく任意のオブジェクト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e6e89-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="e6e89-136">場合は、変数インスタンスを参照していた、設定`Nothing`インスタンス自体を終了しません。</span><span class="sxs-lookup"><span data-stu-id="e6e89-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="e6e89-137">インスタンスが終了し、ガベージ コレクター (GC) が残り、アクティブな参照がないことを検出した後にのみ関連付けられているメモリとシステム リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="e6e89-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="e6e89-138">`Nothing` 異なります、<xref:System.DBNull>初期化されていないバリアントをまたはデータベースが存在しない列を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e6e89-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e89-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6e89-139">See also</span></span>

- [<span data-ttu-id="e6e89-140">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="e6e89-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="e6e89-141">オブジェクトの有効期間:オブジェクトを作成および破棄する方法</span><span class="sxs-lookup"><span data-stu-id="e6e89-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="e6e89-142">Visual Basic での有効期間</span><span class="sxs-lookup"><span data-stu-id="e6e89-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="e6e89-143">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="e6e89-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="e6e89-144">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="e6e89-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="e6e89-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="e6e89-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
