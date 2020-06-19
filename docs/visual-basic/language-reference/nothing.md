---
title: Nothing キーワード
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 3bd4681341a33cc8db4ecbc2b284be243db56549
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344174"
---
# <a name="nothing-keyword-visual-basic"></a><span data-ttu-id="cc077-102">Nothing キーワード (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc077-102">Nothing keyword (Visual Basic)</span></span>

<span data-ttu-id="cc077-103">任意のデータ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="cc077-103">Represents the default value of any data type.</span></span> <span data-ttu-id="cc077-104">参照型の場合、既定値は `null` 参照です。</span><span class="sxs-lookup"><span data-stu-id="cc077-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="cc077-105">値型の場合、既定値は、値型で null が許容されるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cc077-105">For value types, the default value depends on whether the value type is nullable.</span></span>

> [!NOTE]
> <span data-ttu-id="cc077-106">null 非許容値型の場合、Visual Basic の `Nothing` は C# の `null` と異なります。</span><span class="sxs-lookup"><span data-stu-id="cc077-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="cc077-107">Visual Basic で、null 非許容値型の変数を `Nothing` に設定すると、変数は宣言された型の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="cc077-108">C# では、null 非許容値型の変数を `null` に割り当てると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cc077-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc077-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc077-109">Remarks</span></span>

<span data-ttu-id="cc077-110">`Nothing` は、データ型の既定値を表します。</span><span class="sxs-lookup"><span data-stu-id="cc077-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="cc077-111">既定値は、変数が値型であるか、参照型であるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cc077-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>

<span data-ttu-id="cc077-112">"*値型*" の変数には、その値が直接格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="cc077-113">値型には、すべての数値データ型 (`Boolean`、`Char`、`Date`)、すべての構造体、およびすべての列挙型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc077-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="cc077-114">"*参照型*" の変数では、オブジェクトのインスタンスへの参照がメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="cc077-115">参照型には、クラス、配列、デリゲート、および文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc077-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="cc077-116">詳細については、「 [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc077-116">For more information, see [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

<span data-ttu-id="cc077-117">変数が値型の場合、`Nothing` の動作は、変数が null 許容データ型かどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cc077-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="cc077-118">null 許容値型を表すには、型名に `?` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc077-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="cc077-119">`Nothing` を null 許容変数に割り当てると、値が `null` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="cc077-120">詳細と例については、「[null 許容値型](../programming-guide/language-features/data-types/nullable-value-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc077-120">For more information and examples, see [Nullable Value Types](../programming-guide/language-features/data-types/nullable-value-types.md).</span></span>

<span data-ttu-id="cc077-121">変数が null 非許容値型である場合は、その変数に `Nothing` を割り当てると、宣言された型の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="cc077-122">その型に変数メンバーが含まれている場合は、すべて既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="cc077-123">次の例では、スカラー型について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc077-123">The following example illustrates this for scalar types.</span></span>

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

<span data-ttu-id="cc077-124">変数が参照型の場合は、変数に `Nothing` を割り当てると、その変数の型の `null` 参照に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc077-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="cc077-125">`null` 参照に設定されている変数は、どのオブジェクトにも関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="cc077-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="cc077-126">この動作を次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="cc077-126">The following example demonstrates this:</span></span>

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

<span data-ttu-id="cc077-127">参照 (または null 許容値型) 変数が `null` かどうかを確認する場合は、`= Nothing` または `<> Nothing` を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cc077-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="cc077-128">必ず `Is Nothing` または `IsNot Nothing` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cc077-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>

<span data-ttu-id="cc077-129">Visual Basic の文字列の場合、空の文字列は `Nothing` と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="cc077-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="cc077-130">したがって、`"" = Nothing` は true となります。</span><span class="sxs-lookup"><span data-stu-id="cc077-130">Therefore, `"" = Nothing` is true.</span></span>

<span data-ttu-id="cc077-131">次の例は、`Is` 演算子と `IsNot` 演算子を使用する比較を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc077-131">The following example shows comparisons that use the `Is` and `IsNot` operators:</span></span>

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

<span data-ttu-id="cc077-132">`As` 句を使用せずに変数を宣言し、それを `Nothing` に設定すると、変数の型は `Object` になります。</span><span class="sxs-lookup"><span data-stu-id="cc077-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="cc077-133">たとえば、`Dim something = Nothing` などです。</span><span class="sxs-lookup"><span data-stu-id="cc077-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="cc077-134">この場合、`Option Strict` がオンで `Option Infer` がオフであれば、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cc077-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>

<span data-ttu-id="cc077-135">オブジェクト変数に `Nothing` を割り当てると、オブジェクト インスタンスを参照しなくなります。</span><span class="sxs-lookup"><span data-stu-id="cc077-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="cc077-136">変数が以前にインスタンスを参照していた場合、その変数を `Nothing` に設定しても、インスタンス自体は終了しません。</span><span class="sxs-lookup"><span data-stu-id="cc077-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="cc077-137">インスタンスが終了し、そのインスタンスに関連付けられているメモリおよびシステム リソースが解放されるのは、ガベージ コレクター (GC) によってアクティブな参照が残っていないことが検出された後のみです。</span><span class="sxs-lookup"><span data-stu-id="cc077-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>

<span data-ttu-id="cc077-138">`Nothing` は、初期化されていないバリアントまたは存在しないデータベース列を表す <xref:System.DBNull> オブジェクトとは異なります。</span><span class="sxs-lookup"><span data-stu-id="cc077-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc077-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc077-139">See also</span></span>

- [<span data-ttu-id="cc077-140">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="cc077-140">Dim Statement</span></span>](./statements/dim-statement.md)
- [<span data-ttu-id="cc077-141">オブジェクトの有効期間: オブジェクトの作成と破棄</span><span class="sxs-lookup"><span data-stu-id="cc077-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="cc077-142">Visual Basic における有効期間</span><span class="sxs-lookup"><span data-stu-id="cc077-142">Lifetime in Visual Basic</span></span>](../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="cc077-143">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="cc077-143">Is Operator</span></span>](./operators/is-operator.md)
- [<span data-ttu-id="cc077-144">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="cc077-144">IsNot Operator</span></span>](./operators/isnot-operator.md)
- [<span data-ttu-id="cc077-145">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="cc077-145">Nullable Value Types</span></span>](../programming-guide/language-features/data-types/nullable-value-types.md)
