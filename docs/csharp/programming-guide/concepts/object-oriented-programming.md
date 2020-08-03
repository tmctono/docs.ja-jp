---
title: オブジェクト指向プログラミング (C#)
description: C# は、抽象化、カプセル化、継承、ポリモーフィズムなど、オブジェクト指向プログラミングを完全にサポートします。
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 0c5495aefad73a2916ad6e2bd2bf3701d0868f24
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302816"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="835ed-103">オブジェクト指向プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="835ed-103">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="835ed-104">C# は、抽象化、カプセル化、継承、ポリモーフィズムなど、オブジェクト指向プログラミングを完全にサポートします。</span><span class="sxs-lookup"><span data-stu-id="835ed-104">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="835ed-105">"*抽象化*" とは、型コンシューマーから不要な詳細を隠すことです。</span><span class="sxs-lookup"><span data-stu-id="835ed-105">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="835ed-106">"*カプセル化*" とは、関連するプロパティ、メソッド、およびその他のメンバーのグループが 1 つの単位またはオブジェクトとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="835ed-106">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="835ed-107">"*継承*" は、既存のクラスに基づいて新しいクラスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="835ed-107">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="835ed-108">"*ポリモーフィズム*" とは、同じプロパティまたはメソッドを異なる方法で実装している複数のクラスを、交換して使用できることです。</span><span class="sxs-lookup"><span data-stu-id="835ed-108">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="835ed-109">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="835ed-109">Classes and objects</span></span>

<span data-ttu-id="835ed-110">"*クラス*" と "*オブジェクト*" という用語は、オブジェクトの "*型*" とクラスの "*インスタンス*" をそれぞれ意味します。</span><span class="sxs-lookup"><span data-stu-id="835ed-110">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="835ed-111">そのため、オブジェクトを作成する操作は "*インスタンス化*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="835ed-111">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="835ed-112">設計図との対比を使って説明すると、クラスは設計図であり、オブジェクトはその設計図を基にした建築物です。</span><span class="sxs-lookup"><span data-stu-id="835ed-112">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="835ed-113">クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-113">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="835ed-114">C# には "*構造体*" と呼ばれている型もありますが、継承とポリモーフィズムに対応する必要がないときに便利です。</span><span class="sxs-lookup"><span data-stu-id="835ed-114">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="835ed-115">詳細については、「[クラスまたは構造体の選択](../../../standard/design-guidelines/choosing-between-class-and-struct.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-115">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="835ed-116">構造体を定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-116">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="835ed-117">詳細については、キーワードの [class](../../language-reference/keywords/class.md) と [struct](../../language-reference/builtin-types/struct.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-117">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="835ed-118">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="835ed-118">Class members</span></span>

<span data-ttu-id="835ed-119">各クラスには、さまざまな "*クラス メンバー*" を含めることができます。クラス メンバーには、クラスのデータを記述するプロパティ、クラスの動作を定義するメソッド、異なるクラスやオブジェクト間で通信するためのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="835ed-119">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="835ed-120">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="835ed-120">Properties and fields</span></span>

<span data-ttu-id="835ed-121">フィールドとプロパティは、オブジェクトに格納されている情報を表します。</span><span class="sxs-lookup"><span data-stu-id="835ed-121">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="835ed-122">フィールドは、適用されるアクセス修飾子に基づき、直接読み取ったり、設定したりできるという理由から変数と似ています。</span><span class="sxs-lookup"><span data-stu-id="835ed-122">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="835ed-123">クラスのインスタンス内からアクセスできるフィールドを定義するには:</span><span class="sxs-lookup"><span data-stu-id="835ed-123">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="835ed-124">プロパティには `get` と `set` というアクセサーがあります。これによって、値を設定する方法と値を返す方法を細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-124">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="835ed-125">C# では、プロパティ値を格納するプライベート フィールドを作成するか、自動実装プロパティを使用できます。自動実装プロパティでは、値を格納するフィールドが背後で自動的に作成され、プロパティ プロシージャの基本的なロジックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-125">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="835ed-126">自動実装プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-126">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="835ed-127">プロパティ値の読み取りと書き込みのために追加の操作を実行する必要がある場合は、プロパティ値を格納するフィールドを定義し、値を格納および取得する基本的なロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="835ed-127">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="835ed-128">ほとんどのプロパティには、プロパティ値の設定と取得を行うための両方のメソッドまたはプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="835ed-128">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="835ed-129">ただし、読み取り専用または書き込み専用のプロパティを作成して、プロパティの変更や読み取りを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-129">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="835ed-130">C# では、`get` プロパティ メソッドまたは `set` プロパティ メソッドを省略します。</span><span class="sxs-lookup"><span data-stu-id="835ed-130">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="835ed-131">ただし、自動実装プロパティを書き込み専用にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="835ed-131">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="835ed-132">読み取り専用の自動実装プロパティは、それが含まれるクラスのコンストラクターで設定できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-132">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="835ed-133">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="835ed-133">For more information, see:</span></span>

- [<span data-ttu-id="835ed-134">get</span><span class="sxs-lookup"><span data-stu-id="835ed-134">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="835ed-135">set</span><span class="sxs-lookup"><span data-stu-id="835ed-135">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="835ed-136">メソッド</span><span class="sxs-lookup"><span data-stu-id="835ed-136">Methods</span></span>

<span data-ttu-id="835ed-137">"*メソッド*" は、オブジェクトが実行できる処理です。</span><span class="sxs-lookup"><span data-stu-id="835ed-137">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="835ed-138">クラスのメソッドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-138">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="835ed-139">クラスには、同じメソッドに対して、パラメーターの数やパラメーターの型が異なる複数の実装 ("*オーバーロード*") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="835ed-139">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="835ed-140">メソッドをオーバーロードするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-140">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="835ed-141">ほとんどの場合、メソッドはクラス定義内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="835ed-141">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="835ed-142">ただし、C# では、既存のクラスの実際の定義の外部にメソッドを追加できる "*拡張メソッド*" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="835ed-142">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="835ed-143">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="835ed-143">For more information, see:</span></span>

- [<span data-ttu-id="835ed-144">メソッド</span><span class="sxs-lookup"><span data-stu-id="835ed-144">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="835ed-145">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="835ed-145">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="835ed-146">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="835ed-146">Constructors</span></span>

<span data-ttu-id="835ed-147">コンストラクターは、特定の型のオブジェクトを作成するときに自動的に実行されるクラス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="835ed-147">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="835ed-148">コンストラクターは、通常、新しいオブジェクトのデータ メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="835ed-148">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="835ed-149">コンストラクターは、クラスの作成時に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-149">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="835ed-150">また、コンストラクター内のコードは常に、クラス内の他のすべてのコードより先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-150">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="835ed-151">他のメソッドと同じように、コンストラクターにも複数のオーバーロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-151">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="835ed-152">クラスのコンストラクターを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-152">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="835ed-153">詳細については、「[コンストラクター](../classes-and-structs/constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-153">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="835ed-154">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="835ed-154">Finalizers</span></span>

<span data-ttu-id="835ed-155">ファイナライザーは、クラスのインスタンスを破棄するために使います。</span><span class="sxs-lookup"><span data-stu-id="835ed-155">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="835ed-156">.NET では、アプリケーション内のマネージド オブジェクトのメモリの割り当てと解放は、ガベージ コレクターによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-156">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="835ed-157">ただし、アプリケーションで作成されるアンマネージ リソースを適切にクリーンアップするために、ファイナライザーも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="835ed-157">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="835ed-158">1 つのクラスに定義できるファイナライザーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="835ed-158">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="835ed-159">.NET のファイナライザーとガベージ コレクションの詳細については、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-159">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="835ed-160">イベント</span><span class="sxs-lookup"><span data-stu-id="835ed-160">Events</span></span>

<span data-ttu-id="835ed-161">クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="835ed-161">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="835ed-162">イベントを送信する (発生させる) クラスは "*パブリッシャー*" と呼ばれ、イベントを受信する (処理する) クラスは "*サブスクライバー*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="835ed-162">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="835ed-163">イベント、およびイベントの発生と処理の詳細については、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="835ed-163">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="835ed-164">クラスでイベントを宣言するには、[event](../../language-reference/keywords/event.md) キーワードを使います。</span><span class="sxs-lookup"><span data-stu-id="835ed-164">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="835ed-165">イベントを発生させるには、イベント デリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="835ed-165">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="835ed-166">イベントをサブスクライブするには、`+=` 演算子を使用します。イベント サブスクリプションを解除するには、`-=` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="835ed-166">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="835ed-167">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="835ed-167">Nested classes</span></span>

<span data-ttu-id="835ed-168">別のクラス内で定義されているクラスを "*入れ子になったクラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="835ed-168">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="835ed-169">既定では、入れ子になったクラスはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="835ed-169">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="835ed-170">入れ子になったクラスのインスタンスを作成するには、コンテナー クラスの名前に続けて、ドットと入れ子になったクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="835ed-170">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="835ed-171">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="835ed-171">Access modifiers and access levels</span></span>

<span data-ttu-id="835ed-172">すべてのクラスおよびクラス メンバーでは、"*アクセス修飾子*" を使って、他のクラスに提供するアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-172">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="835ed-173">次のアクセス修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-173">The following access modifiers are available:</span></span>

| <span data-ttu-id="835ed-174">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="835ed-174">C# Modifier</span></span> | <span data-ttu-id="835ed-175">定義</span><span class="sxs-lookup"><span data-stu-id="835ed-175">Definition</span></span> |
|--|--|
| [<span data-ttu-id="835ed-176">public</span><span class="sxs-lookup"><span data-stu-id="835ed-176">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="835ed-177">この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-177">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="835ed-178">private</span><span class="sxs-lookup"><span data-stu-id="835ed-178">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="835ed-179">この型またはメンバーには、同じクラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-179">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="835ed-180">protected</span><span class="sxs-lookup"><span data-stu-id="835ed-180">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="835ed-181">この型またはメンバーには、同じクラスまたは派生クラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-181">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="835ed-182">internal</span><span class="sxs-lookup"><span data-stu-id="835ed-182">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="835ed-183">この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="835ed-183">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="835ed-184">protected internal</span><span class="sxs-lookup"><span data-stu-id="835ed-184">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="835ed-185">この型またはメンバーには、同じアセンブリ内の任意のコード、または別のアセンブリ内の任意の派生クラスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-185">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="835ed-186">private protected</span><span class="sxs-lookup"><span data-stu-id="835ed-186">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="835ed-187">この型またはメンバーには、基底クラス アセンブリ内の同じクラスまたは派生クラスのコードがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-187">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="835ed-188">詳細については、「[アクセス修飾子](../classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-188">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="835ed-189">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="835ed-189">Instantiating classes</span></span>

<span data-ttu-id="835ed-190">オブジェクトを作成するには、クラスをインスタンス化する (クラスのインスタンスを作成する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="835ed-190">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="835ed-191">クラスをインスタンス化した後は、インスタンスのプロパティやフィールドに値を割り当てたり、クラスのメソッドを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-191">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="835ed-192">クラスのインスタンス化のプロセスでプロパティに値を割り当てるには、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="835ed-192">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="835ed-193">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="835ed-193">For more information, see:</span></span>

- [<span data-ttu-id="835ed-194">new 演算子</span><span class="sxs-lookup"><span data-stu-id="835ed-194">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="835ed-195">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="835ed-195">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="835ed-196">静的クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="835ed-196">Static Classes and Members</span></span>

<span data-ttu-id="835ed-197">クラスの静的メンバーは、クラスのすべてのインスタンスで共有されるプロパティ、プロシージャ、またはフィールドです。</span><span class="sxs-lookup"><span data-stu-id="835ed-197">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="835ed-198">静的メンバーを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-198">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="835ed-199">静的メンバーにアクセスするには、クラスのオブジェクトを作成せずにクラスの名前を使います。</span><span class="sxs-lookup"><span data-stu-id="835ed-199">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="835ed-200">C# の静的クラスには静的メンバーだけがあり、インスタンス化することはできません。</span><span class="sxs-lookup"><span data-stu-id="835ed-200">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="835ed-201">また、静的メンバーから、非静的のプロパティ、フィールド、またはメソッドにアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="835ed-201">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="835ed-202">詳しくは、「[static](../../language-reference/keywords/static.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="835ed-202">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="835ed-203">匿名型</span><span class="sxs-lookup"><span data-stu-id="835ed-203">Anonymous types</span></span>

<span data-ttu-id="835ed-204">匿名型を使用すると、データ型のクラス定義を記述せずにオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-204">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="835ed-205">クラスは、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-205">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="835ed-206">このクラスには使用可能な名前がなく、オブジェクトの宣言時に指定したプロパティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-206">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="835ed-207">匿名型のインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-207">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="835ed-208">詳細については次を参照してください:[匿名型](../classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="835ed-208">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="835ed-209">継承</span><span class="sxs-lookup"><span data-stu-id="835ed-209">Inheritance</span></span>

<span data-ttu-id="835ed-210">継承を使用すると、他のクラスで定義されている動作を再利用、拡張、および変更する新しいクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-210">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="835ed-211">メンバーが継承される側のクラスを "*基底クラス*" と呼び、メンバーを継承する側のクラスを "*派生クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="835ed-211">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="835ed-212">ただし、C# のすべてのクラスは、.NET のクラス階層構造をサポートしてすべてのクラスに下位レベルのサービスを提供する <xref:System.Object> クラスを暗黙的に継承します。</span><span class="sxs-lookup"><span data-stu-id="835ed-212">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="835ed-213">C# は多重継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="835ed-213">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="835ed-214">つまり、派生クラスに対して指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="835ed-214">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="835ed-215">基底クラスを継承するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-215">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="835ed-216">既定では、すべてのクラスが継承可能になります。</span><span class="sxs-lookup"><span data-stu-id="835ed-216">By default all classes can be inherited.</span></span> <span data-ttu-id="835ed-217">ただし、クラスを基底クラスとして使用できないように指定したり、基底クラスとしてのみ使用できるクラスを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="835ed-217">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="835ed-218">クラスを基底クラスとして使用できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-218">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="835ed-219">クラスが基底クラスとしてのみ使用され、インスタンス化できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-219">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="835ed-220">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="835ed-220">For more information, see:</span></span>

- [<span data-ttu-id="835ed-221">sealed</span><span class="sxs-lookup"><span data-stu-id="835ed-221">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="835ed-222">abstract</span><span class="sxs-lookup"><span data-stu-id="835ed-222">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="835ed-223">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="835ed-223">Overriding Members</span></span>

<span data-ttu-id="835ed-224">既定では、派生クラスは基底クラスのすべてのメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="835ed-224">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="835ed-225">継承したメンバーの動作を変更する場合は、そのメンバーをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="835ed-225">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="835ed-226">つまり、派生クラスに、メソッド、プロパティ、またはイベントの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-226">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="835ed-227">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="835ed-227">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="835ed-228">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="835ed-228">C# Modifier</span></span> | <span data-ttu-id="835ed-229">定義</span><span class="sxs-lookup"><span data-stu-id="835ed-229">Definition</span></span> |
|--|--|
| [<span data-ttu-id="835ed-230">virtual</span><span class="sxs-lookup"><span data-stu-id="835ed-230">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="835ed-231">派生クラスでのクラス メンバーのオーバーライドを許可します。</span><span class="sxs-lookup"><span data-stu-id="835ed-231">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="835ed-232">override</span><span class="sxs-lookup"><span data-stu-id="835ed-232">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="835ed-233">基底クラスで定義されている仮想メンバー (オーバーライドできるメンバー) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="835ed-233">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="835ed-234">abstract</span><span class="sxs-lookup"><span data-stu-id="835ed-234">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="835ed-235">派生クラスでのクラス メンバーのオーバーライドを必須にします。</span><span class="sxs-lookup"><span data-stu-id="835ed-235">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="835ed-236">new 修飾子</span><span class="sxs-lookup"><span data-stu-id="835ed-236">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="835ed-237">基底クラスから継承されたメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="835ed-237">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="835ed-238">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="835ed-238">Interfaces</span></span>

<span data-ttu-id="835ed-239">インターフェイスは、クラスと同様にプロパティ、メソッド、およびイベントのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="835ed-239">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="835ed-240">ただし、クラスとは異なり、インターフェイスは実装を提供しません。</span><span class="sxs-lookup"><span data-stu-id="835ed-240">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="835ed-241">インターフェイスはクラスによって実装され、クラスとは別のエンティティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-241">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="835ed-242">インターフェイスを実装するクラスは、そのインターフェイスのあらゆる機能を定義に従って厳密に実装する必要があります。この点で、インターフェイスはコントラクトを表しています。</span><span class="sxs-lookup"><span data-stu-id="835ed-242">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="835ed-243">インターフェイスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-243">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="835ed-244">クラスにインターフェイスを実装するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-244">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="835ed-245">詳細については、プログラミング ガイド記事の[インターフェイス](../interfaces/index.md)に関する箇所と言語参照記事の [interface](../../language-reference/keywords/interface.md) というキーワードに関する箇所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-245">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="835ed-246">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="835ed-246">Generics</span></span>

<span data-ttu-id="835ed-247">.NET のクラス、構造体、インターフェイス、およびメソッドには、格納または使用できるオブジェクトの型を定義する "*型パラメーター*" を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="835ed-247">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="835ed-248">ジェネリックの最も一般的な例として、コレクションがあります。コレクションには、その中に格納されるオブジェクトの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-248">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="835ed-249">ジェネリック クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-249">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="835ed-250">ジェネリック クラスのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-250">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="835ed-251">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="835ed-251">For more information, see:</span></span>

- [<span data-ttu-id="835ed-252">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="835ed-252">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="835ed-253">ジェネリック - C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="835ed-253">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="835ed-254">デリゲート</span><span class="sxs-lookup"><span data-stu-id="835ed-254">Delegates</span></span>

<span data-ttu-id="835ed-255">"*デリゲート*" は、メソッド シグネチャを定義する型であり、互換性のあるシグネチャを持つ任意のメソッドへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="835ed-255">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="835ed-256">メソッドは、デリゲートを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="835ed-256">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="835ed-257">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="835ed-257">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="835ed-258">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="835ed-258">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="835ed-259">デリゲートを使用したイベント処理について詳しくは、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="835ed-259">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="835ed-260">デリゲートを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-260">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="835ed-261">デリゲートで指定されたシグネチャに一致するメソッドへの参照を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="835ed-261">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
    {
        // Add code here.
    }

    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="835ed-262">詳細については、プログラミング ガイド記事の[デリゲート](../delegates/index.md)に関する箇所と言語参照記事の [delegate](../../language-reference/builtin-types/reference-types.md) というキーワードに関する箇所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="835ed-262">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="835ed-263">関連項目</span><span class="sxs-lookup"><span data-stu-id="835ed-263">See also</span></span>

- [<span data-ttu-id="835ed-264">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="835ed-264">C# Programming Guide</span></span>](../index.md)
