---
title: where (ジェネリック型制約) - C# リファレンス
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 19bf7682916336173ed93619fb6f0ff1242a1b30
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712807"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="a6bf6-102">where (ジェネリック型制約) (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a6bf6-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="a6bf6-103">ジェネリック定義の `where` 句では、型の制約を指定します。この型は、ジェネリック型、メソッド、デリゲート、またはローカル関数における型パラメーターの引数として使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="a6bf6-104">制約では、インターフェイス (基底クラス) を指定したり、参照、値、またはアンマネージド型となるジェネリック型を要求したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value, or unmanaged type.</span></span> <span data-ttu-id="a6bf6-105">それらにより型引数が処理する必要がある機能が宣言されえます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="a6bf6-106">たとえば、型パラメーター `T` が <xref:System.IComparable%601> インターフェイスを実装するように、次のように `MyGenericClass` ジェネリック クラスを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="a6bf6-107">クエリ式での where 句の詳細については、「[where 句](where-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="a6bf6-108">`where` 句には基底クラスの制約を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="a6bf6-109">基底クラスの制約は、ジェネリック型の型引数として使用する型には、ジェネリック型の型引数として使用される基底クラスとして指定されているクラス (または基底クラス自体) が含まれている必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="a6bf6-110">基底クラスの制約を使用する場合は、型パラメーターに関する制約よりも前に制約を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="a6bf6-111">一部の型は、基底クラスの制約として許可されません (<xref:System.Object>、<xref:System.Array>、<xref:System.ValueType>)。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="a6bf6-112">C# 7.3 より前は、<xref:System.Enum>、<xref:System.Delegate>、<xref:System.MulticastDelegate> も基底クラスの制約として許可されていません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="a6bf6-113">次の例では、この型は基底クラスとして指定できるようになったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="a6bf6-114">`where` 句では、型が `class` または `struct` であることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="a6bf6-115">`struct` 制約では、`System.ValueType` の基底クラスの制約を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="a6bf6-116">`System.ValueType` 型は基底クラスの制約として使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="a6bf6-117">`class` 制約と `struct` 制約の両方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="a6bf6-118">`where` 句には、`notnull` 制約を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-118">The `where` clause may include the `notnull` constraint.</span></span> <span data-ttu-id="a6bf6-119">`notnull` 制約では、型パラメーターを null 非許容型に制限します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-119">The `notnull` constraint limits the type parameter to non-nullable types.</span></span> <span data-ttu-id="a6bf6-120">その型には、[値型](struct.md)または null 非許容参照型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-120">That type may be a [value type](struct.md) or a non-nullable reference type.</span></span> <span data-ttu-id="a6bf6-121">`notnull` 制約は、C# 8.0 以降の [`nullable enable` コンテキスト](../../nullable-references.md#nullable-contexts)でコンパイルされたコードで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-121">The `notnull` constraint is available starting in C# 8.0 for code compiled in a [`nullable enable` context](../../nullable-references.md#nullable-contexts).</span></span> <span data-ttu-id="a6bf6-122">他の制約とは異なり、型引数が `notnull` 制約に違反すると、コンパイラによりエラーではなく警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-122">Unlike other constraints, if a type argument violates the `notnull` constraint, the compiler generates a warning instead of an error.</span></span> <span data-ttu-id="a6bf6-123">警告は、`nullable enable` コンテキストでのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-123">Warnings are only generated in a `nullable enable` context.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a6bf6-124">`notnull` 制約が含まれるジェネリック宣言は、null 許容が未指定のコンテキストで使用できますが、コンパイラではその制約は強制されません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-124">Generic declarations that include the `notnull` constraint can be used in a nullable oblivious context, but compiler does not enforce the constraint.</span></span>

[!code-csharp[using the nonnull constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#NotNull)]

<span data-ttu-id="a6bf6-125">`where` 句には、`unmanaged` 制約を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-125">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="a6bf6-126">`unmanaged` 制約では、[アンマネージド型](../builtin-types/unmanaged-types.md)と呼ばれる型に対して型パラメーターを制限します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-126">The `unmanaged` constraint limits the type parameter to types known as [unmanaged types](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="a6bf6-127">`unmanaged` 制約を使用すると、C# でローレベルの相互運用コードを記述しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-127">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="a6bf6-128">この制約では、すべてのアンマネージド型にわたって再利用可能なルーチンを可能にします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-128">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="a6bf6-129">`unmanaged` 制約は、`class` や `struct` 制約と組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-129">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="a6bf6-130">`unmanaged` 制約は `struct` にする必要がある型を適用します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-130">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="a6bf6-131">`where` 句には、コンストラクター制約 `new()` を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-131">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="a6bf6-132">その制約では、`new` 演算子を使用して型パラメーターのインスタンスを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-132">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="a6bf6-133">[new() 制約](new-constraint.md)に基づいて、コンパイラで、指定されている型引数にはアクセス可能なパラメーターなしのコンストラクターが必要であることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-133">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless constructor.</span></span> <span data-ttu-id="a6bf6-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-134">For example:</span></span>

[!code-csharp[using the new constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="a6bf6-135">`new()` 制約は `where` 句の最後に示されます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-135">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="a6bf6-136">`new()` 制約は、`struct` や `unmanaged` 制約と組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-136">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="a6bf6-137">それらの制約を満たすすべての型には、`new()` 制約を重複させて、アクセス可能なパラメーターなしのコンストラクターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-137">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="a6bf6-138">複数の型パラメーターがある場合には、型パラメーターごとに `where` 句を 1 つずつ使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-138">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="a6bf6-139">次の例に示すように、ジェネリック メソッドの型パラメーターにも制約を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-139">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="a6bf6-140">デリゲートに対する型パラメーター制約を記述する構文は、メソッドの構文と同じである点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-140">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="a6bf6-141">汎用デリゲートについては、「[汎用デリゲート](../../programming-guide/generics/generic-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-141">For information on generic delegates, see [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="a6bf6-142">制約の構文と使用方法の詳細については、「[型パラメーターの制約](../../programming-guide/generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bf6-142">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a6bf6-143">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a6bf6-143">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a6bf6-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6bf6-144">See also</span></span>

- [<span data-ttu-id="a6bf6-145">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a6bf6-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a6bf6-146">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a6bf6-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a6bf6-147">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="a6bf6-147">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
- [<span data-ttu-id="a6bf6-148">new 制約</span><span class="sxs-lookup"><span data-stu-id="a6bf6-148">new Constraint</span></span>](./new-constraint.md)
- [<span data-ttu-id="a6bf6-149">型パラメーターの制約</span><span class="sxs-lookup"><span data-stu-id="a6bf6-149">Constraints on Type Parameters</span></span>](../../programming-guide/generics/constraints-on-type-parameters.md)
