---
title: オブジェクト指向プログラミング (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 1de150f6eb4be893ca1afce6bd16afde5752c986
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711817"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="16ffd-102">オブジェクト指向プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="16ffd-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="16ffd-103">C# は、カプセル化、継承、ポリモーフィズムなど、オブジェクト指向プログラミングを完全にサポートします。</span><span class="sxs-lookup"><span data-stu-id="16ffd-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="16ffd-104">"*カプセル化*" とは、関連するプロパティ、メソッド、およびその他のメンバーのグループが 1 つの単位またはオブジェクトとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="16ffd-105">"*継承*" は、既存のクラスに基づいて新しいクラスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="16ffd-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="16ffd-106">"*ポリモーフィズム*" とは、同じプロパティまたはメソッドを異なる方法で実装している複数のクラスを、交換して使用できることです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="16ffd-107">このセクションでは、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="16ffd-108">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="16ffd-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="16ffd-109">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="16ffd-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="16ffd-110">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="16ffd-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="16ffd-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="16ffd-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="16ffd-112">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="16ffd-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="16ffd-113">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="16ffd-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="16ffd-114">イベント</span><span class="sxs-lookup"><span data-stu-id="16ffd-114">Events</span></span>](#Events)

    - [<span data-ttu-id="16ffd-115">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="16ffd-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="16ffd-116">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="16ffd-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="16ffd-117">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="16ffd-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="16ffd-118">静的クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="16ffd-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="16ffd-119">匿名型</span><span class="sxs-lookup"><span data-stu-id="16ffd-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="16ffd-120">継承</span><span class="sxs-lookup"><span data-stu-id="16ffd-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="16ffd-121">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="16ffd-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="16ffd-122">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16ffd-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="16ffd-123">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="16ffd-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="16ffd-124">デリゲート</span><span class="sxs-lookup"><span data-stu-id="16ffd-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="16ffd-125">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="16ffd-125">Classes and Objects</span></span>

<span data-ttu-id="16ffd-126">"*クラス*" という用語と "*オブジェクト*" という用語は同じ意味で使われる場合がありますが、実際には、クラスはオブジェクトの "*型*" を表すのに対し、オブジェクトはクラスの使用可能な "*インスタンス*" です。</span><span class="sxs-lookup"><span data-stu-id="16ffd-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="16ffd-127">そのため、オブジェクトを作成する操作は "*インスタンス化*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="16ffd-128">設計図との対比を使って説明すると、クラスは設計図であり、オブジェクトはその設計図を基にした建築物です。</span><span class="sxs-lookup"><span data-stu-id="16ffd-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="16ffd-129">クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="16ffd-130">C# には、"*構造体*" と呼ばれる軽量バージョンのクラスも用意されています。構造体は、大きいオブジェクト配列を作成する必要があり、その配列に使用されるメモリの量を抑えたい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="16ffd-131">構造体を定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="16ffd-132">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-132">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-133">class</span><span class="sxs-lookup"><span data-stu-id="16ffd-133">class</span></span>](../../language-reference/keywords/class.md)

- [<span data-ttu-id="16ffd-134">struct</span><span class="sxs-lookup"><span data-stu-id="16ffd-134">struct</span></span>](../../language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="16ffd-135">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="16ffd-135">Class Members</span></span>

<span data-ttu-id="16ffd-136">各クラスには、さまざまな "*クラス メンバー*" を含めることができます。クラス メンバーには、クラスのデータを記述するプロパティ、クラスの動作を定義するメソッド、異なるクラスやオブジェクト間で通信するためのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="16ffd-137">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="16ffd-137">Properties and Fields</span></span>

<span data-ttu-id="16ffd-138">フィールドとプロパティは、オブジェクトに格納されている情報を表します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="16ffd-139">フィールドは、直接読み取ったり設定したりできるので変数と似ています。</span><span class="sxs-lookup"><span data-stu-id="16ffd-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="16ffd-140">フィールドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="16ffd-141">プロパティには get プロシージャと set プロシージャがあり、これらを使用することで値の設定方法や戻り値をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="16ffd-142">C# では、プロパティ値を格納するプライベート フィールドを作成するか、または自動実装プロパティと呼ばれる手法を使用できます。自動実装プロパティでは、値を格納するフィールドが背後で自動的に作成され、プロパティ プロシージャの基本的なロジックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="16ffd-143">自動実装プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="16ffd-144">プロパティ値の読み取りと書き込みのために追加の操作を実行する必要がある場合は、プロパティ値を格納するフィールドを定義し、値を格納および取得する基本的なロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="16ffd-145">ほとんどのプロパティには、プロパティ値の設定と取得を行うための両方のメソッドまたはプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="16ffd-146">ただし、読み取り専用または書き込み専用のプロパティを作成して、プロパティの変更や読み取りを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="16ffd-147">C# では、`get` プロパティ メソッドまたは `set` プロパティ メソッドを省略します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="16ffd-148">ただし、自動実装プロパティを読み取り専用または書き込み専用にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="16ffd-149">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-149">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-150">get</span><span class="sxs-lookup"><span data-stu-id="16ffd-150">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="16ffd-151">set</span><span class="sxs-lookup"><span data-stu-id="16ffd-151">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="16ffd-152">メソッド</span><span class="sxs-lookup"><span data-stu-id="16ffd-152">Methods</span></span>

<span data-ttu-id="16ffd-153">"*メソッド*" は、オブジェクトが実行できる処理です。</span><span class="sxs-lookup"><span data-stu-id="16ffd-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="16ffd-154">クラスのメソッドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="16ffd-155">クラスには、同じメソッドに対して、パラメーターの数やパラメーターの型が異なる複数の実装 ("*オーバーロード*") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="16ffd-156">メソッドをオーバーロードするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="16ffd-157">ほとんどの場合、メソッドはクラス定義内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="16ffd-158">ただし、C# では、既存のクラスの実際の定義の外部にメソッドを追加できる "*拡張メソッド*" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="16ffd-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="16ffd-159">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-159">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-160">メソッド</span><span class="sxs-lookup"><span data-stu-id="16ffd-160">Methods</span></span>](../classes-and-structs/methods.md)

- [<span data-ttu-id="16ffd-161">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="16ffd-161">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="16ffd-162">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="16ffd-162">Constructors</span></span>

<span data-ttu-id="16ffd-163">コンストラクターは、特定の型のオブジェクトを作成するときに自動的に実行されるクラス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="16ffd-164">コンストラクターは、通常、新しいオブジェクトのデータ メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="16ffd-165">コンストラクターは、クラスの作成時に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="16ffd-166">また、コンストラクター内のコードは常に、クラス内の他のすべてのコードより先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="16ffd-167">他のメソッドと同じように、コンストラクターにも複数のオーバーロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="16ffd-168">クラスのコンストラクターを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="16ffd-169">詳細については、「[コンストラクター](../classes-and-structs/constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-169">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="16ffd-170">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="16ffd-170">Finalizers</span></span>

<span data-ttu-id="16ffd-171">ファイナライザーは、クラスのインスタンスを破棄するために使います。</span><span class="sxs-lookup"><span data-stu-id="16ffd-171">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="16ffd-172">.NET Framework では、アプリケーション内のマネージド オブジェクトのメモリの割り当てと解放は、ガベージ コレクターによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-172">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="16ffd-173">ただし、アプリケーションで作成されるアンマネージ リソースを適切にクリーンアップするために、ファイナライザーも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-173">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="16ffd-174">1 つのクラスに定義できるファイナライザーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-174">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="16ffd-175">.NET Framework のファイナライザーおよびガベージ コレクションについて詳しくは、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-175">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="16ffd-176">イベント</span><span class="sxs-lookup"><span data-stu-id="16ffd-176">Events</span></span>

<span data-ttu-id="16ffd-177">クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-177">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="16ffd-178">イベントを送信する (発生させる) クラスは "*パブリッシャー*" と呼ばれ、イベントを受信する (処理する) クラスは "*サブスクライバー*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-178">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="16ffd-179">イベント、およびイベントの発生と処理の詳細については、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-179">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="16ffd-180">クラスでイベントを宣言するには、[event](../../language-reference/keywords/event.md) キーワードを使います。</span><span class="sxs-lookup"><span data-stu-id="16ffd-180">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="16ffd-181">イベントを発生させるには、イベント デリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-181">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="16ffd-182">イベントをサブスクライブするには、`+=` 演算子を使用します。イベント サブスクリプションを解除するには、`-=` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-182">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="16ffd-183">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="16ffd-183">Nested Classes</span></span>

<span data-ttu-id="16ffd-184">別のクラス内で定義されているクラスを "*入れ子になったクラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-184">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="16ffd-185">既定では、入れ子になったクラスはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-185">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="16ffd-186">入れ子になったクラスのインスタンスを作成するには、コンテナー クラスの名前に続けて、ドットと入れ子になったクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-186">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="16ffd-187">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="16ffd-187">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="16ffd-188">すべてのクラスおよびクラス メンバーでは、"*アクセス修飾子*" を使って、他のクラスに提供するアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-188">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="16ffd-189">次のアクセス修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-189">The following access modifiers are available:</span></span>

|<span data-ttu-id="16ffd-190">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="16ffd-190">C# Modifier</span></span>|<span data-ttu-id="16ffd-191">定義</span><span class="sxs-lookup"><span data-stu-id="16ffd-191">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="16ffd-192">public</span><span class="sxs-lookup"><span data-stu-id="16ffd-192">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="16ffd-193">この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-193">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="16ffd-194">private</span><span class="sxs-lookup"><span data-stu-id="16ffd-194">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="16ffd-195">この型またはメンバーには、同じクラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-195">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="16ffd-196">protected</span><span class="sxs-lookup"><span data-stu-id="16ffd-196">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="16ffd-197">この型またはメンバーには、同じクラスまたは派生クラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-197">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="16ffd-198">internal</span><span class="sxs-lookup"><span data-stu-id="16ffd-198">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="16ffd-199">この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-199">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="16ffd-200">protected internal</span><span class="sxs-lookup"><span data-stu-id="16ffd-200">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="16ffd-201">この型またはメンバーには、同じアセンブリ内の任意のコード、または別のアセンブリ内の任意の派生クラスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="16ffd-202">private protected</span><span class="sxs-lookup"><span data-stu-id="16ffd-202">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="16ffd-203">この型またはメンバーには、基底クラス アセンブリ内の同じクラスまたは派生クラスのコードがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-203">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="16ffd-204">詳細については、「[アクセス修飾子](../classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-204">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="16ffd-205">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="16ffd-205">Instantiating Classes</span></span>

<span data-ttu-id="16ffd-206">オブジェクトを作成するには、クラスをインスタンス化する (クラスのインスタンスを作成する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-206">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="16ffd-207">クラスをインスタンス化した後は、インスタンスのプロパティやフィールドに値を割り当てたり、クラスのメソッドを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-207">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="16ffd-208">クラスのインスタンス化のプロセスでプロパティに値を割り当てるには、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-208">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="16ffd-209">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-209">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-210">new 演算子</span><span class="sxs-lookup"><span data-stu-id="16ffd-210">new Operator</span></span>](../../language-reference/operators/new-operator.md)

- [<span data-ttu-id="16ffd-211">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="16ffd-211">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="16ffd-212">静的クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="16ffd-212">Static Classes and Members</span></span>

<span data-ttu-id="16ffd-213">クラスの静的メンバーは、クラスのすべてのインスタンスで共有されるプロパティ、プロシージャ、またはフィールドです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-213">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="16ffd-214">静的メンバーを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-214">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="16ffd-215">静的メンバーにアクセスするには、クラスのオブジェクトを作成せずにクラスの名前を使います。</span><span class="sxs-lookup"><span data-stu-id="16ffd-215">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="16ffd-216">C# の静的クラスには静的メンバーだけがあり、インスタンス化することはできません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-216">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="16ffd-217">また、静的メンバーから、非静的のプロパティ、フィールド、またはメソッドにアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-217">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="16ffd-218">詳しくは、「[static](../../language-reference/keywords/static.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-218">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="16ffd-219">匿名型</span><span class="sxs-lookup"><span data-stu-id="16ffd-219">Anonymous Types</span></span>

<span data-ttu-id="16ffd-220">匿名型を使用すると、データ型のクラス定義を記述せずにオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-220">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="16ffd-221">クラスは、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-221">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="16ffd-222">このクラスには使用可能な名前がなく、オブジェクトの宣言時に指定したプロパティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-222">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="16ffd-223">匿名型のインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-223">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="16ffd-224">詳細については次を参照してください:[匿名型](../classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="16ffd-224">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="16ffd-225">継承</span><span class="sxs-lookup"><span data-stu-id="16ffd-225">Inheritance</span></span>

<span data-ttu-id="16ffd-226">継承を使用すると、他のクラスで定義されている動作を再利用、拡張、および変更する新しいクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-226">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="16ffd-227">メンバーが継承される側のクラスを "*基底クラス*" と呼び、メンバーを継承する側のクラスを "*派生クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-227">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="16ffd-228">ただし、C# のすべてのクラスは、.NET のクラス階層構造をサポートしてすべてのクラスに下位レベルのサービスを提供する <xref:System.Object> クラスを暗黙的に継承します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-228">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="16ffd-229">C# は多重継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-229">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="16ffd-230">つまり、派生クラスに対して指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="16ffd-230">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="16ffd-231">基底クラスを継承するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-231">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="16ffd-232">既定では、すべてのクラスが継承可能になります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-232">By default all classes can be inherited.</span></span> <span data-ttu-id="16ffd-233">ただし、クラスを基底クラスとして使用できないように指定したり、基底クラスとしてのみ使用できるクラスを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-233">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="16ffd-234">クラスを基底クラスとして使用できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-234">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="16ffd-235">クラスが基底クラスとしてのみ使用され、インスタンス化できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-235">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="16ffd-236">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-236">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-237">sealed</span><span class="sxs-lookup"><span data-stu-id="16ffd-237">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="16ffd-238">abstract</span><span class="sxs-lookup"><span data-stu-id="16ffd-238">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="16ffd-239">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="16ffd-239">Overriding Members</span></span>

<span data-ttu-id="16ffd-240">既定では、派生クラスは基底クラスのすべてのメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-240">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="16ffd-241">継承したメンバーの動作を変更する場合は、そのメンバーをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ffd-241">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="16ffd-242">つまり、派生クラスに、メソッド、プロパティ、またはイベントの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-242">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="16ffd-243">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-243">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="16ffd-244">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="16ffd-244">C# Modifier</span></span>|<span data-ttu-id="16ffd-245">定義</span><span class="sxs-lookup"><span data-stu-id="16ffd-245">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="16ffd-246">virtual</span><span class="sxs-lookup"><span data-stu-id="16ffd-246">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="16ffd-247">派生クラスでのクラス メンバーのオーバーライドを許可します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-247">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="16ffd-248">override</span><span class="sxs-lookup"><span data-stu-id="16ffd-248">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="16ffd-249">基底クラスで定義されている仮想メンバー (オーバーライドできるメンバー) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="16ffd-249">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="16ffd-250">abstract</span><span class="sxs-lookup"><span data-stu-id="16ffd-250">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="16ffd-251">派生クラスでのクラス メンバーのオーバーライドを必須にします。</span><span class="sxs-lookup"><span data-stu-id="16ffd-251">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="16ffd-252">new 修飾子</span><span class="sxs-lookup"><span data-stu-id="16ffd-252">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="16ffd-253">基底クラスから継承されたメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="16ffd-253">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="16ffd-254">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16ffd-254">Interfaces</span></span>

<span data-ttu-id="16ffd-255">インターフェイスは、クラスと同様にプロパティ、メソッド、およびイベントのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-255">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="16ffd-256">ただし、クラスとは異なり、インターフェイスは実装を提供しません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-256">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="16ffd-257">インターフェイスはクラスによって実装され、クラスとは別のエンティティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-257">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="16ffd-258">インターフェイスを実装するクラスは、そのインターフェイスのあらゆる機能を定義に従って厳密に実装する必要があります。この点で、インターフェイスはコントラクトを表しています。</span><span class="sxs-lookup"><span data-stu-id="16ffd-258">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="16ffd-259">インターフェイスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-259">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="16ffd-260">クラスにインターフェイスを実装するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-260">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="16ffd-261">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-261">For more information, see:</span></span>

[<span data-ttu-id="16ffd-262">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16ffd-262">Interfaces</span></span>](../interfaces/index.md)

[<span data-ttu-id="16ffd-263">interface</span><span class="sxs-lookup"><span data-stu-id="16ffd-263">interface</span></span>](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="16ffd-264">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="16ffd-264">Generics</span></span>

<span data-ttu-id="16ffd-265">.NET Framework のクラス、構造体、インターフェイス、およびメソッドは、格納または使用できるオブジェクトの型を定義する "*型パラメーター*" を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-265">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="16ffd-266">ジェネリックの最も一般的な例として、コレクションがあります。コレクションには、その中に格納されるオブジェクトの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-266">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="16ffd-267">ジェネリック クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-267">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="16ffd-268">ジェネリック クラスのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-268">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="16ffd-269">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-269">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-270">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="16ffd-270">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="16ffd-271">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="16ffd-271">Generics</span></span>](../generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="16ffd-272">デリゲート</span><span class="sxs-lookup"><span data-stu-id="16ffd-272">Delegates</span></span>

<span data-ttu-id="16ffd-273">"*デリゲート*" は、メソッド シグネチャを定義する型であり、互換性のあるシグネチャを持つ任意のメソッドへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-273">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="16ffd-274">メソッドは、デリゲートを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-274">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="16ffd-275">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="16ffd-275">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="16ffd-276">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="16ffd-276">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="16ffd-277">デリゲートを使用したイベント処理について詳しくは、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16ffd-277">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="16ffd-278">デリゲートを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-278">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="16ffd-279">デリゲートで指定されたシグネチャに一致するメソッドへの参照を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16ffd-279">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
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

<span data-ttu-id="16ffd-280">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="16ffd-280">For more information, see:</span></span>

- [<span data-ttu-id="16ffd-281">デリゲート</span><span class="sxs-lookup"><span data-stu-id="16ffd-281">Delegates</span></span>](../delegates/index.md)

- [<span data-ttu-id="16ffd-282">delegate</span><span class="sxs-lookup"><span data-stu-id="16ffd-282">delegate</span></span>](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="16ffd-283">関連項目</span><span class="sxs-lookup"><span data-stu-id="16ffd-283">See also</span></span>

- [<span data-ttu-id="16ffd-284">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="16ffd-284">C# Programming Guide</span></span>](../index.md)
