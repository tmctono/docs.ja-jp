---
title: ポリモーフィズム - C# プログラミング ガイド
description: 基底クラスと派生クラスの関係を説明する C# などのオブジェクト指向プログラミング言語の重要な概念であるポリモーフィズムについて説明します。
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 59b5f5d2d5a8f274845607aeca370c316670bd68
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925450"
---
# <a name="polymorphism-c-programming-guide"></a><span data-ttu-id="71806-103">ポリモーフィズム (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="71806-103">Polymorphism (C# Programming Guide)</span></span>

<span data-ttu-id="71806-104">ポリモーフィズムは、カプセル化と継承に次ぐ、オブジェクト指向プログラミングの第 3 の柱と言われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="71806-104">Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance.</span></span> <span data-ttu-id="71806-105">ポリモーフィズムは、ギリシャ語で "多形" を意味し、次の 2 つの側面を持っています。</span><span class="sxs-lookup"><span data-stu-id="71806-105">Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:</span></span>
  
- <span data-ttu-id="71806-106">メソッド パラメーター、コレクション、配列などに渡された派生クラスのオブジェクトは、実行時に基底クラスのオブジェクトとして扱われることがあります。</span><span class="sxs-lookup"><span data-stu-id="71806-106">At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays.</span></span> <span data-ttu-id="71806-107">このポリモーフィズムが発生すると、オブジェクトの宣言された型はその実行時の型と同じではなくなります。</span><span class="sxs-lookup"><span data-stu-id="71806-107">When this polymorphism occurs, the object's declared type is no longer identical to its run-time type.</span></span>
- <span data-ttu-id="71806-108">基底クラスでは、"[virtual](../../language-reference/keywords/virtual.md) *メソッド*" を定義して実行できます。派生クラスでそれを[オーバーライド](../../language-reference/keywords/override.md)すると、独自の定義と実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="71806-108">Base classes may define and implement [virtual](../../language-reference/keywords/virtual.md) *methods*, and derived classes can [override](../../language-reference/keywords/override.md) them, which means they provide their own definition and implementation.</span></span> <span data-ttu-id="71806-109">実行時には、クライアント コードがメソッドを呼び出したとき、CLR によってオブジェクトの実行時の型が検索され、仮想メソッドのオーバーライドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71806-109">At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method.</span></span> <span data-ttu-id="71806-110">ソース コード内で、基底クラスでメソッドを呼び出し、そのメソッドの派生クラス版を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="71806-110">In your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.</span></span>

<span data-ttu-id="71806-111">仮想メソッドを使用すると、関連するオブジェクトのグループを同一の方法で扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="71806-111">Virtual methods enable you to work with groups of related objects in a uniform way.</span></span> <span data-ttu-id="71806-112">たとえば、描画サーフェイスにさまざまな種類の図形を作成できる描画アプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="71806-112">For example, suppose you have a drawing application that enables a user to create various kinds of shapes on a drawing surface.</span></span> <span data-ttu-id="71806-113">コンパイル時には、ユーザーがどのような種類の図形を作成するかわかりません。</span><span class="sxs-lookup"><span data-stu-id="71806-113">You do not know at compile time which specific types of shapes the user will create.</span></span> <span data-ttu-id="71806-114">しかし、アプリケーションでは、作成されたさまざまな種類の図形を追跡し、ユーザーのマウス操作に応じて更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71806-114">However, the application has to keep track of all the various types of shapes that are created, and it has to update them in response to user mouse actions.</span></span> <span data-ttu-id="71806-115">ポリモーフィズムを使用すると、2 つの基本的な手順でこの問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="71806-115">You can use polymorphism to solve this problem in two basic steps:</span></span>

1. <span data-ttu-id="71806-116">各図形クラスが共通の基底クラスから派生するようなクラス階層を作成します。</span><span class="sxs-lookup"><span data-stu-id="71806-116">Create a class hierarchy in which each specific shape class derives from a common base class.</span></span>
1. <span data-ttu-id="71806-117">仮想メソッドを使用して、基底クラスの 1 つのメソッドを呼び出すことで、派生クラスの適切なメソッドが呼び出されるようにします。</span><span class="sxs-lookup"><span data-stu-id="71806-117">Use a virtual method to invoke the appropriate method on any derived class through a single call to the base class method.</span></span>

<span data-ttu-id="71806-118">まず、`Shape` という基底クラスと、`Rectangle`、`Circle`、`Triangle` などの派生クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="71806-118">First, create a base class called `Shape`, and derived classes such as `Rectangle`, `Circle`, and `Triangle`.</span></span> <span data-ttu-id="71806-119">`Shape` クラスで `Draw` という仮想メソッドを定義し、各派生クラスでそれをオーバーライドして、そのクラスが表す特定の図形を描画します。</span><span class="sxs-lookup"><span data-stu-id="71806-119">Give the `Shape` class a virtual method called `Draw`, and override it in each derived class to draw the particular shape that the class represents.</span></span> <span data-ttu-id="71806-120">`List<Shape>` オブジェクトを作成し、`Circle`、`Triangle`、`Rectangle` をそれに追加します。</span><span class="sxs-lookup"><span data-stu-id="71806-120">Create a `List<Shape>` object and add a `Circle`, `Triangle`, and `Rectangle` to it.</span></span>

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

<span data-ttu-id="71806-121">描画サーフェイスを更新するには、[foreach](../../language-reference/keywords/foreach-in.md) ループを使用してリストを反復処理し、リスト内の各 `Shape` オブジェクトの `Draw` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="71806-121">To update the drawing surface, use a [foreach](../../language-reference/keywords/foreach-in.md) loop to iterate through the list and call the `Draw` method on each `Shape` object in the list.</span></span> <span data-ttu-id="71806-122">リスト内の各オブジェクトの宣言された型は `Shape` ですが、呼び出されるのは実行時の型 (それぞれの派生クラスでオーバーライドされたメソッド) になります。</span><span class="sxs-lookup"><span data-stu-id="71806-122">Even though each object in the list has a declared type of `Shape`, it's the run-time type (the overridden version of the method in each derived class) that will be invoked.</span></span>

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

<span data-ttu-id="71806-123">C# では、すべての型がポリモーフィックです。これは、ユーザー定義型を含むすべての型が <xref:System.Object> から派生するためです。</span><span class="sxs-lookup"><span data-stu-id="71806-123">In C#, every type is polymorphic because all types, including user-defined types, inherit from <xref:System.Object>.</span></span>  

## <a name="polymorphism-overview"></a><span data-ttu-id="71806-124">ポリモーフィズムの概要</span><span class="sxs-lookup"><span data-stu-id="71806-124">Polymorphism overview</span></span>

### <a name="virtual-members"></a><span data-ttu-id="71806-125">仮想メンバー</span><span class="sxs-lookup"><span data-stu-id="71806-125">Virtual members</span></span>

<span data-ttu-id="71806-126">基底クラスから派生クラスを継承すると、派生クラスでは、基底クラスのすべてのメソッド、フィールド、プロパティ、イベントが継承されます。</span><span class="sxs-lookup"><span data-stu-id="71806-126">When a derived class inherits from a base class, it gains all the methods, fields, properties, and events of the base class.</span></span> <span data-ttu-id="71806-127">派生クラスを設計するとき、仮想メソッドの動作についてはさまざまな選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="71806-127">The designer of the derived class has different choices for the behavior of virtual methods:</span></span>

- <span data-ttu-id="71806-128">派生クラスでは基底クラスの仮想メンバーがオーバーライドされ、新しい動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="71806-128">The derived class may override virtual members in the base class, defining new behavior.</span></span>
- <span data-ttu-id="71806-129">派生クラスでは最も近い基底クラス メソッドがオーバーライドされることなく継承され、既存の動作が維持されますが、さらに派生したクラスではメソッドをオーバーライドできるようになります。</span><span class="sxs-lookup"><span data-stu-id="71806-129">The derived class inherit the closest base class method without overriding it, preserving the existing behavior but enabling further derived classes to override the method.</span></span>
- <span data-ttu-id="71806-130">派生クラスでは、基底クラスの実装を隠ぺいするメンバーの非仮想実装を新しく定義できます。</span><span class="sxs-lookup"><span data-stu-id="71806-130">The derived class may define new non-virtual implementation of those members that hide the base class implementations.</span></span>

<span data-ttu-id="71806-131">派生クラスが基底クラスのメンバーをオーバーライドできるのは、基底クラスのメンバーが [virtual](../../language-reference/keywords/virtual.md) または [abstract](../../language-reference/keywords/abstract.md) として宣言されている場合だけです。</span><span class="sxs-lookup"><span data-stu-id="71806-131">A derived class can override a base class member only if the base class member is declared as [virtual](../../language-reference/keywords/virtual.md) or [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="71806-132">派生メンバーでは、[override](../../language-reference/keywords/override.md) キーワードを使用して、そのメソッドが仮想呼び出しに加わることを明示的に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="71806-132">The derived member must use the [override](../../language-reference/keywords/override.md) keyword to explicitly indicate that the method is intended to participate in virtual invocation.</span></span> <span data-ttu-id="71806-133">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-133">The following code provides an example:</span></span>

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

<span data-ttu-id="71806-134">フィールドは仮想にできません。仮想にできるのは、メソッド、プロパティ、イベント、インデクサーに限られます。</span><span class="sxs-lookup"><span data-stu-id="71806-134">Fields cannot be virtual; only methods, properties, events, and indexers can be virtual.</span></span> <span data-ttu-id="71806-135">派生クラスが仮想メンバーをオーバーライドすると、派生クラスのメンバーは、そのクラスのインスタンスが基底クラスのインスタンスとしてアクセスされるときでも呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71806-135">When a derived class overrides a virtual member, that member is called even when an instance of that class is being accessed as an instance of the base class.</span></span> <span data-ttu-id="71806-136">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-136">The following code provides an example:</span></span>

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#SnippetTestVirtualMethods)]

<span data-ttu-id="71806-137">仮想メソッドとプロパティを使用すると、派生クラスは、基底クラスのメソッドの実装を使用せずに基底クラスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="71806-137">Virtual methods and properties enable derived classes to extend a base class without needing to use the base class implementation of a method.</span></span> <span data-ttu-id="71806-138">詳細については、「[Override キーワードと New キーワードによるバージョン管理](./versioning-with-the-override-and-new-keywords.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71806-138">For more information, see [Versioning with the Override and New Keywords](./versioning-with-the-override-and-new-keywords.md).</span></span> <span data-ttu-id="71806-139">1 つまたは一連のメソッドを定義し、その実装を派生クラスに任せるもう 1 つの方法として、インターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="71806-139">An interface provides another way to define a method or set of methods whose implementation is left to derived classes.</span></span> <span data-ttu-id="71806-140">詳細については、「[インターフェイス](../interfaces/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71806-140">For more information, see [Interfaces](../interfaces/index.md).</span></span>

### <a name="hide-base-class-members-with-new-members"></a><span data-ttu-id="71806-141">新しいメンバーで基底クラス メンバーを隠ぺいする</span><span class="sxs-lookup"><span data-stu-id="71806-141">Hide base class members with new members</span></span>

<span data-ttu-id="71806-142">基底クラスのメンバーと同じ名前を持つメンバーを派生クラスに与える場合、[new](../../language-reference/keywords/new-modifier.md) キーワードを使用し、基底クラス メンバーを隠ぺいできます。</span><span class="sxs-lookup"><span data-stu-id="71806-142">If you want your derived class to have a member with the same name as a member in a base class, you can use the [new](../../language-reference/keywords/new-modifier.md) keyword to hide the base class member.</span></span> <span data-ttu-id="71806-143">`new` キーワードは、置き換えられるクラス メンバーの戻り値の型の前に配置します。</span><span class="sxs-lookup"><span data-stu-id="71806-143">The `new` keyword is put before the return type of a class member that is being replaced.</span></span> <span data-ttu-id="71806-144">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-144">The following code provides an example:</span></span>

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

<span data-ttu-id="71806-145">基底クラスのメンバーが隠ぺいされても、派生クラスのインスタンスを基底クラスのインスタンスに型変換することで、クライアント コードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="71806-145">Hidden base class members may be accessed from client code by casting the instance of the derived class to an instance of the base class.</span></span> <span data-ttu-id="71806-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-146">For example:</span></span>

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a><span data-ttu-id="71806-147">派生クラスで仮想メンバーのオーバーライドを禁止する</span><span class="sxs-lookup"><span data-stu-id="71806-147">Prevent derived classes from overriding virtual members</span></span>  

<span data-ttu-id="71806-148">仮想メンバーとそれを最初に宣言したクラスの間で宣言されているクラスの数に関係なく、仮想メンバーは仮想のままになります。</span><span class="sxs-lookup"><span data-stu-id="71806-148">Virtual members remain virtual, regardless of how many classes have been declared between the virtual member and the class that originally declared it.</span></span> <span data-ttu-id="71806-149">クラス `A` で仮想メンバーが宣言され、クラス `B` が `A` から派生し、クラス `C` が `B` から派生した場合、クラス `C` では仮想メンバーが継承され、そのメンバーのオーバーライドがクラス `B` で宣言されたかどうかに関係なく、仮想メンバーをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="71806-149">If class `A` declares a virtual member, and class `B` derives from `A`, and class `C` derives from `B`, class `C` inherits the virtual member, and may override it, regardless of whether class `B` declared an override for that member.</span></span> <span data-ttu-id="71806-150">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-150">The following code provides an example:</span></span>

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

<span data-ttu-id="71806-151">派生クラスでは、オーバーライドを [sealed](../../language-reference/keywords/sealed.md) として宣言することで仮想継承を中止できます。</span><span class="sxs-lookup"><span data-stu-id="71806-151">A derived class can stop virtual inheritance by declaring an override as [sealed](../../language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="71806-152">継承を止めるには、クラス メンバーの宣言で、`override` キーワードの前に `sealed` キーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71806-152">Stopping inheritance requires putting the `sealed` keyword before the `override` keyword in the class member declaration.</span></span> <span data-ttu-id="71806-153">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-153">The following code provides an example:</span></span>

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

<span data-ttu-id="71806-154">上の例では、メソッド `DoWork` は `C` から派生したあらゆるクラスに対して仮想になりません。</span><span class="sxs-lookup"><span data-stu-id="71806-154">In the previous example, the method `DoWork` is no longer virtual to any class derived from `C`.</span></span> <span data-ttu-id="71806-155">`C` のインスタンスの場合、型 `B` や型 `A` に型変換されたとしてでも、依然として仮想となります。</span><span class="sxs-lookup"><span data-stu-id="71806-155">It's still virtual for instances of `C`, even if they're cast to type `B` or type `A`.</span></span> <span data-ttu-id="71806-156">シール メソッドは、次のコード例に示すように、`new` キーワードを使用して派生クラスに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="71806-156">Sealed methods can be replaced by derived classes by using the `new` keyword, as the following example shows:</span></span>

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

<span data-ttu-id="71806-157">この場合、型 `D` の変数を利用して `D` で `DoWork` が呼び出されたとき、新しい `DoWork` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71806-157">In this case, if `DoWork` is called on `D` using a variable of type `D`, the new `DoWork` is called.</span></span> <span data-ttu-id="71806-158">型 `C`、`B`、`A` の変数が `D` のインスタンスにアクセスする目的で使用される場合、`DoWork` の呼び出しは仮想継承の規則に準拠し、クラス `C` での `DoWork` の実装に呼び出しが転送されます。</span><span class="sxs-lookup"><span data-stu-id="71806-158">If a variable of type `C`, `B`, or `A` is used to access an instance of `D`, a call to `DoWork` will follow the rules of virtual inheritance, routing those calls to the implementation of `DoWork` on class `C`.</span></span>

### <a name="access-base-class-virtual-members-from-derived-classes"></a><span data-ttu-id="71806-159">派生クラスから基底クラスの仮想メンバーにアクセスする</span><span class="sxs-lookup"><span data-stu-id="71806-159">Access base class virtual members from derived classes</span></span>

<span data-ttu-id="71806-160">メソッドやプロパティを置き換えたり、オーバーライドしたりした派生クラスでは、`base` キーワードを使用して、基底クラスのメソッドやプロパティに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="71806-160">A derived class that has replaced or overridden a method or property can still access the method or property on the base class using the `base` keyword.</span></span> <span data-ttu-id="71806-161">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="71806-161">The following code provides an example:</span></span>

```csharp
public class Base
{
    public virtual void DoWork() {/*...*/ }
}
public class Derived : Base
{
    public override void DoWork()
    {
        //Perform Derived's work here
        //...
        // Call DoWork on base class
        base.DoWork();
    }
}
```

<span data-ttu-id="71806-162">詳細については、「[base](../../language-reference/keywords/base.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71806-162">For more information, see [base](../../language-reference/keywords/base.md).</span></span>

> [!NOTE]
> <span data-ttu-id="71806-163">仮想メンバーの場合、その固有の実装で `base` を使用して、その仮想メンバーの基底クラス実装を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71806-163">It is recommended that virtual members use `base` to call the base class implementation of that member in their own implementation.</span></span> <span data-ttu-id="71806-164">基底クラスの動作を実行できるようにすることで、派生クラスは、派生クラスに固有の動作を実装することに集中できます。</span><span class="sxs-lookup"><span data-stu-id="71806-164">Letting the base class behavior occur enables the derived class to concentrate on implementing behavior specific to the derived class.</span></span> <span data-ttu-id="71806-165">基底クラス実装を呼び出さない場合は、基底クラスの動作と互換性のある動作を派生クラスで実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71806-165">If the base class implementation is not called, it is up to the derived class to make their behavior compatible with the behavior of the base class.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="71806-166">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="71806-166">In this section</span></span>

- [<span data-ttu-id="71806-167">Override キーワードと New キーワードによるバージョン管理</span><span class="sxs-lookup"><span data-stu-id="71806-167">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="71806-168">Override キーワードと New キーワードを使用する場合について</span><span class="sxs-lookup"><span data-stu-id="71806-168">Knowing When to Use Override and New Keywords</span></span>](./knowing-when-to-use-override-and-new-keywords.md)
- [<span data-ttu-id="71806-169">ToString メソッドをオーバーライドする方法</span><span class="sxs-lookup"><span data-stu-id="71806-169">How to override the ToString method</span></span>](./how-to-override-the-tostring-method.md)

## <a name="see-also"></a><span data-ttu-id="71806-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="71806-170">See also</span></span>

- [<span data-ttu-id="71806-171">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="71806-171">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="71806-172">継承</span><span class="sxs-lookup"><span data-stu-id="71806-172">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="71806-173">抽象クラスとシール クラス、およびクラス メンバー</span><span class="sxs-lookup"><span data-stu-id="71806-173">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="71806-174">メソッド</span><span class="sxs-lookup"><span data-stu-id="71806-174">Methods</span></span>](./methods.md)
- [<span data-ttu-id="71806-175">イベント</span><span class="sxs-lookup"><span data-stu-id="71806-175">Events</span></span>](../events/index.md)
- [<span data-ttu-id="71806-176">プロパティ</span><span class="sxs-lookup"><span data-stu-id="71806-176">Properties</span></span>](./properties.md)
- [<span data-ttu-id="71806-177">インデクサー</span><span class="sxs-lookup"><span data-stu-id="71806-177">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="71806-178">型</span><span class="sxs-lookup"><span data-stu-id="71806-178">Types</span></span>](../types/index.md)
