---
title: class キーワード - C# リファレンス
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673096"
---
# <a name="class-c-reference"></a><span data-ttu-id="3212e-102">class (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3212e-102">class (C# Reference)</span></span>

<span data-ttu-id="3212e-103">クラスは、次の例に示すように、キーワード `class` を使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="3212e-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="3212e-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="3212e-104">Remarks</span></span>

<span data-ttu-id="3212e-105">C# では、単一継承のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3212e-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="3212e-106">つまり、クラスは 1 つの基底クラスの実装だけを継承できます。</span><span class="sxs-lookup"><span data-stu-id="3212e-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="3212e-107">ただし、クラスは複数のインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="3212e-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="3212e-108">クラスの継承とインターフェイスの実装の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3212e-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="3212e-109">継承</span><span class="sxs-lookup"><span data-stu-id="3212e-109">Inheritance</span></span>|<span data-ttu-id="3212e-110">例</span><span class="sxs-lookup"><span data-stu-id="3212e-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="3212e-111">None</span><span class="sxs-lookup"><span data-stu-id="3212e-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="3212e-112">Single</span><span class="sxs-lookup"><span data-stu-id="3212e-112">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="3212e-113">なし。2 つのインターフェイスを実装</span><span class="sxs-lookup"><span data-stu-id="3212e-113">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="3212e-114">1 つ。1 つのインターフェイスを実装</span><span class="sxs-lookup"><span data-stu-id="3212e-114">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="3212e-115">名前空間内で直接宣言され、他のクラスに入れ子にされていないクラスは、[public](./public.md) または [internal](./internal.md) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="3212e-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="3212e-116">クラスは既定で `internal` です。</span><span class="sxs-lookup"><span data-stu-id="3212e-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="3212e-117">クラスのメンバー (入れ子にされているクラスを含む) は [public](public.md)、[protected internal](protected-internal.md)、[protected](protected.md)、[internal](internal.md)、[private](private.md)、または [private protected](private-protected.md) のいずれかとして宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="3212e-117">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="3212e-118">メンバーは既定で `private` です。</span><span class="sxs-lookup"><span data-stu-id="3212e-118">Members are `private` by default.</span></span>

<span data-ttu-id="3212e-119">詳細については、「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3212e-119">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="3212e-120">型パラメーターを持つジェネリック クラスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="3212e-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="3212e-121">詳細については、「[ジェネリック クラス](../../programming-guide/generics/generic-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3212e-121">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="3212e-122">クラスには、次のメンバーの宣言を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3212e-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="3212e-123">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="3212e-123">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="3212e-124">定数</span><span class="sxs-lookup"><span data-stu-id="3212e-124">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="3212e-125">フィールド</span><span class="sxs-lookup"><span data-stu-id="3212e-125">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="3212e-126">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="3212e-126">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="3212e-127">メソッド</span><span class="sxs-lookup"><span data-stu-id="3212e-127">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="3212e-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3212e-128">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="3212e-129">インデクサー</span><span class="sxs-lookup"><span data-stu-id="3212e-129">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="3212e-130">演算子</span><span class="sxs-lookup"><span data-stu-id="3212e-130">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="3212e-131">イベント</span><span class="sxs-lookup"><span data-stu-id="3212e-131">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="3212e-132">デリゲート</span><span class="sxs-lookup"><span data-stu-id="3212e-132">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="3212e-133">クラス</span><span class="sxs-lookup"><span data-stu-id="3212e-133">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="3212e-134">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3212e-134">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="3212e-135">構造体型</span><span class="sxs-lookup"><span data-stu-id="3212e-135">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="3212e-136">列挙型</span><span class="sxs-lookup"><span data-stu-id="3212e-136">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="3212e-137">例</span><span class="sxs-lookup"><span data-stu-id="3212e-137">Example</span></span>

<span data-ttu-id="3212e-138">ここでは、クラスのフィールド、コンストラクター、メソッドの宣言例を示します。</span><span class="sxs-lookup"><span data-stu-id="3212e-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="3212e-139">また、オブジェクト インスタンスの作成とインスタンス データの出力の例も示します。</span><span class="sxs-lookup"><span data-stu-id="3212e-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="3212e-140">次の例では、2 つのクラスが宣言されています。</span><span class="sxs-lookup"><span data-stu-id="3212e-140">In this example, two classes are declared.</span></span> <span data-ttu-id="3212e-141">最初の `Child` クラスには、2 つのプライベート フィールド (`name` と `age`)、2 つのパブリック コンストラクター、および 1 つのパブリック メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="3212e-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="3212e-142">2 番目のクラスである `StringTest` は、`Main`の格納に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3212e-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="3212e-143">コメント</span><span class="sxs-lookup"><span data-stu-id="3212e-143">Comments</span></span>

<span data-ttu-id="3212e-144">前の例で、プライベート フィールド (`name` および `age`) にアクセスできるのは、`Child` クラスのパブリック メソッドだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3212e-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="3212e-145">たとえば、次のステートメントを使用して `Main` メソッドから子の名前を印刷することはできません。</span><span class="sxs-lookup"><span data-stu-id="3212e-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="3212e-146">`Main` から `Child`のプライベート メンバーへのアクセスは、`Main` がそのクラスのメンバーである場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="3212e-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="3212e-147">アクセス修飾子を指定せずにクラス内で宣言された型は既定で `private` になります。そのため、キーワードが削除されてもこの例のデータ メンバーは `private` です。</span><span class="sxs-lookup"><span data-stu-id="3212e-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="3212e-148">最後に、パラメーターなしのコンストラクターを使って作成したオブジェクト (`child3`) の `age` フィールドが、既定で 0 に初期化されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3212e-148">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3212e-149">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="3212e-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3212e-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="3212e-150">See also</span></span>

- [<span data-ttu-id="3212e-151">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3212e-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3212e-152">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3212e-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3212e-153">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="3212e-153">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="3212e-154">参照型</span><span class="sxs-lookup"><span data-stu-id="3212e-154">Reference Types</span></span>](./reference-types.md)
