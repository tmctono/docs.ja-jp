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
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963757"
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="6ef9b-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="6ef9b-103">任意のデータ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-103">Represents the default value of any data type.</span></span> <span data-ttu-id="6ef9b-104">参照型の場合、既定値は`null`参照です。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="6ef9b-105">値型の場合、既定値は、値型が null 値を許容するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ef9b-106">Null 非許容の値型の`Nothing`場合、Visual Basic の`null`はC#とでは異なります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="6ef9b-107">Visual Basic で、null 非許容の値型の変数をに`Nothing`設定すると、変数は宣言された型の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="6ef9b-108">でC#は、null 非許容の値型の変数をに`null`割り当てた場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef9b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ef9b-109">Remarks</span></span>  
 <span data-ttu-id="6ef9b-110">`Nothing`データ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="6ef9b-111">既定値は、変数が値型であるか、参照型であるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="6ef9b-112">*値型*の変数には、その値が直接含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="6ef9b-113">値型には、すべての数値`Boolean`データ`Char`型`Date`、、、、すべての構造体、およびすべての列挙が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="6ef9b-114">*参照型*の変数は、メモリ内のオブジェクトのインスタンスへの参照を格納します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="6ef9b-115">参照型には、クラス、配列、デリゲート、および文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="6ef9b-116">詳細については、「 [値型と参照型](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="6ef9b-117">変数が値型の場合、の`Nothing`動作は、変数が null 許容型かどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="6ef9b-118">Null 許容値型を表すには、 `?`型名に修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="6ef9b-119">Null `Nothing`許容変数に割り当てると、値が`null`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="6ef9b-120">詳細と例については、「 [Null 許容値型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="6ef9b-121">変数が null 値が許容されない値型である場合`Nothing` 、に割り当てると、宣言された型の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="6ef9b-122">その型に変数メンバーが含まれている場合は、すべてが既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="6ef9b-123">次の例では、スカラー型について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 <span data-ttu-id="6ef9b-124">変数が参照型の場合、変数にを`Nothing`割り当てると、変数の型の`null`参照に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="6ef9b-125">`null`参照に設定されている変数は、どのオブジェクトにも関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="6ef9b-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 <span data-ttu-id="6ef9b-127">参照 (または null 許容値型) 変数が`null`であるかどうかを確認する場合は、または`<> Nothing`を使用`= Nothing`しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="6ef9b-128">常に`Is Nothing`また`IsNot Nothing`はを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="6ef9b-129">Visual Basic 内の文字列の場合、空の`Nothing`文字列はと等しくなります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="6ef9b-130">したがって`"" = Nothing` 、は true になります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="6ef9b-131">次の例は、演算子`Is`と`IsNot`演算子を使用する比較を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 <span data-ttu-id="6ef9b-132">`As`句を使用せずに変数を宣言し、に設定`Nothing`すると、 `Object`変数の型はになります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="6ef9b-133">たとえば、の`Dim something = Nothing`ようになります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="6ef9b-134">この場合`Option Strict` 、がオンになっていて、がオフ`Option Infer`になっていると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="6ef9b-135">をオブジェクト変数`Nothing`に割り当てると、オブジェクトインスタンスを参照しなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="6ef9b-136">変数が以前にインスタンスを参照していた場合、 `Nothing`に設定すると、インスタンス自体は終了しません。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="6ef9b-137">インスタンスが終了し、そのインスタンスに関連付けられているメモリおよびシステムリソースが解放されるのは、ガベージコレクター (GC) によってアクティブな参照が残っていないことが検出された後のみです。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="6ef9b-138">`Nothing`は、初期<xref:System.DBNull>化されていない variant または存在しないデータベース列を表すオブジェクトとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef9b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ef9b-139">See also</span></span>

- [<span data-ttu-id="6ef9b-140">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="6ef9b-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="6ef9b-141">オブジェクトの有効期間:オブジェクトの作成方法と破棄方法</span><span class="sxs-lookup"><span data-stu-id="6ef9b-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="6ef9b-142">Visual Basic の有効期間</span><span class="sxs-lookup"><span data-stu-id="6ef9b-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="6ef9b-143">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="6ef9b-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="6ef9b-144">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="6ef9b-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="6ef9b-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="6ef9b-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
