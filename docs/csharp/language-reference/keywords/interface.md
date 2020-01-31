---
title: インターフェイス - C# リファレンス
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: b315d1f04c9e74700afba8ee7871b23ab4b2fd28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744683"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="d8056-102">:::no-loc text="interface"::: (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d8056-102">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="d8056-103">インターフェイスによりコントラクトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="d8056-103">An interface defines a contract.</span></span> <span data-ttu-id="d8056-104">そのコントラクトを実装する [`class`](class.md) または [`struct`](struct.md) では、インターフェイスで定義されているメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8056-104">Any [`class`](class.md) or [`struct`](struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="d8056-105">C# 8.0 以降では、インターフェイスによってメンバーの既定の実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-105">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="d8056-106">共通の機能を 1 回で実装する目的で [`static`](static.md) メンバーも定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-106">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="d8056-107">次の例の `ImplementationClass` クラスは、`SampleMethod` を返す、パラメーターのない `void` メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8056-107">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="d8056-108">使用例を含む詳細については、「[インターフェイス](../../programming-guide/interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8056-108">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="d8056-109">例</span><span class="sxs-lookup"><span data-stu-id="d8056-109">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="d8056-110">インターフェイスには、名前空間またはクラスのメンバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-110">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="d8056-111">インターフェイス宣言には、次のメンバーの宣言を含めることができます (実装なしのシグネチャ)。</span><span class="sxs-lookup"><span data-stu-id="d8056-111">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="d8056-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8056-112">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="d8056-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8056-113">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="d8056-114">インデクサー</span><span class="sxs-lookup"><span data-stu-id="d8056-114">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="d8056-115">イベント</span><span class="sxs-lookup"><span data-stu-id="d8056-115">Events</span></span>](event.md)

<span data-ttu-id="d8056-116">これらのメンバー宣言には通常、本文が含まれません。</span><span class="sxs-lookup"><span data-stu-id="d8056-116">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="d8056-117">C# 8.0 以降では、インターフェイス メンバーで本文を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-117">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="d8056-118">これは*既定の実装*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="d8056-118">This is called a *default implementation*.</span></span> <span data-ttu-id="d8056-119">本文のあるメンバーでは、実装がオーバーライドされないクラスおよび構造体に "既定の" 実装を与えることがインターフェイスに許可されます。</span><span class="sxs-lookup"><span data-stu-id="d8056-119">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="d8056-120">また、C# 8.0 以降、インターフェイスには次を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8056-120">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="d8056-121">定数</span><span class="sxs-lookup"><span data-stu-id="d8056-121">Constants</span></span>](const.md)
- [<span data-ttu-id="d8056-122">演算子</span><span class="sxs-lookup"><span data-stu-id="d8056-122">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="d8056-123">[静的コンストラクター](../../programming-guide/classes-and-structs/constructors.md#static-constructors)。</span><span class="sxs-lookup"><span data-stu-id="d8056-123">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="d8056-124">入れ子にされた型</span><span class="sxs-lookup"><span data-stu-id="d8056-124">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- [<span data-ttu-id="d8056-125">静的フィールド、メソッド、プロパティ、インデクサー、イベント</span><span class="sxs-lookup"><span data-stu-id="d8056-125">Static fields, methods, properties, indexers, and events</span></span>](static.md)
- <span data-ttu-id="d8056-126">明示的なインターフェイス実装構文を使用するメンバー宣言。</span><span class="sxs-lookup"><span data-stu-id="d8056-126">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="d8056-127">明示的なアクセス修飾子 (既定のアクセスは [`public`](access-modifiers.md))。</span><span class="sxs-lookup"><span data-stu-id="d8056-127">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="d8056-128">インターフェイスには、インスタンスの状態を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8056-128">Interfaces may not contain instance state.</span></span> <span data-ttu-id="d8056-129">静的フィールドが許可されるようになりましたが、インスタンス フィールドはインターフェイスでは許可されません。</span><span class="sxs-lookup"><span data-stu-id="d8056-129">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="d8056-130">[インスタンスの自動プロパティ](../../programming-guide/classes-and-structs/auto-implemented-properties.md)では暗黙的に隠しフィールドが宣言されることがあり、インターフェイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8056-130">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="d8056-131">このルールは、プロパティの宣言に微細な影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="d8056-131">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="d8056-132">インターフェイス宣言では、次のコードによって、`class` や `struct` の場合のように自動実装プロパティが宣言されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d8056-132">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="d8056-133">その代わり、既定の実装が与えられないが、インターフェイスを実装する何らかの型で実装する必要があるプロパティが宣言されます。</span><span class="sxs-lookup"><span data-stu-id="d8056-133">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="d8056-134">インターフェイスは、1 つ以上の基底インターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-134">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="d8056-135">あるインターフェイスで基底インターフェイスに実装されている[メソッドがオーバーライドされる](override.md)とき、そのインターフェイスでは[明示的なインターフェイス実装](../../programming-guide/interfaces/explicit-interface-implementation.md)構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8056-135">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="d8056-136">基本型のリストに基底クラスとインターフェイスが含まれる場合は、基底クラスがリストの最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8056-136">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="d8056-137">インターフェイスを実装するクラスは、そのインターフェイスのメンバーを明示的に実装できます。</span><span class="sxs-lookup"><span data-stu-id="d8056-137">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="d8056-138">明示的に実装されているメンバーには、クラス インスタンスではアクセスできません。インターフェイスのインスタンスを使用した場合にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8056-138">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="d8056-139">また、既定のインターフェイス メンバーには、インターフェイスのインスタンス経由でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8056-139">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="d8056-140">明示的なインターフェイス実装の詳細については、「[明示的なインターフェイスの実装](../../programming-guide/interfaces/explicit-interface-implementation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8056-140">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="d8056-141">例</span><span class="sxs-lookup"><span data-stu-id="d8056-141">Example</span></span>

<span data-ttu-id="d8056-142">ここでは、インターフェイスの実装例を示します。</span><span class="sxs-lookup"><span data-stu-id="d8056-142">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="d8056-143">この例では、インターフェイスにプロパティ宣言が含まれ、クラスに実装が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8056-143">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="d8056-144">`IPoint` を実装するクラスのインスタンスには、整数プロパティ `x` および `y` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8056-144">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="d8056-145">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d8056-145">C# language specification</span></span>

<span data-ttu-id="d8056-146">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[インターフェイス](~/_csharplang/spec/interfaces.md)」セクションと [C# 8.0 の既定のインターフェイス メンバー](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8056-146">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="d8056-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8056-147">See also</span></span>

- [<span data-ttu-id="d8056-148">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8056-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8056-149">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d8056-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8056-150">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d8056-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d8056-151">参照型</span><span class="sxs-lookup"><span data-stu-id="d8056-151">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="d8056-152">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8056-152">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="d8056-153">プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="d8056-153">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="d8056-154">インデクサーの使用</span><span class="sxs-lookup"><span data-stu-id="d8056-154">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="d8056-155">class</span><span class="sxs-lookup"><span data-stu-id="d8056-155">class</span></span>](class.md)
- [<span data-ttu-id="d8056-156">struct</span><span class="sxs-lookup"><span data-stu-id="d8056-156">struct</span></span>](struct.md)
- [<span data-ttu-id="d8056-157">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8056-157">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
