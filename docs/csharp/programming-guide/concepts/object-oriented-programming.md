---
title: オブジェクト指向プログラミング (C#)
ms.date: 02/08/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 01d6f55bf0752f902f351675c4596abbb8ac85c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627891"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="2ee9d-102">オブジェクト指向プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="2ee9d-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="2ee9d-103">C# は、カプセル化、継承、ポリモーフィズムなど、オブジェクト指向プログラミングを完全にサポートします。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="2ee9d-104">"*カプセル化*" とは、関連するプロパティ、メソッド、およびその他のメンバーのグループが 1 つの単位またはオブジェクトとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="2ee9d-105">"*継承*" は、既存のクラスに基づいて新しいクラスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="2ee9d-106">"*ポリモーフィズム*" とは、同じプロパティまたはメソッドを異なる方法で実装している複数のクラスを、交換して使用できることです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="2ee9d-107">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2ee9d-107">Classes and objects</span></span>

<span data-ttu-id="2ee9d-108">"*クラス*" と "*オブジェクト*" という用語は、オブジェクトの "*型*" とクラスの "*インスタンス*" をそれぞれ意味します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-108">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="2ee9d-109">そのため、オブジェクトを作成する操作は "*インスタンス化*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-109">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="2ee9d-110">設計図との対比を使って説明すると、クラスは設計図であり、オブジェクトはその設計図を基にした建築物です。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-110">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="2ee9d-111">クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-111">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="2ee9d-112">C# には "*構造体*" と呼ばれている型もありますが、継承とポリモーフィズムに対応する必要がないときに便利です。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-112">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span>

<span data-ttu-id="2ee9d-113">構造体を定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-113">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="2ee9d-114">詳細については、キーワードの [class](../../language-reference/keywords/class.md) と [struct](../../language-reference/builtin-types/struct.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-114">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="2ee9d-115">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="2ee9d-115">Class members</span></span>

<span data-ttu-id="2ee9d-116">各クラスには、さまざまな "*クラス メンバー*" を含めることができます。クラス メンバーには、クラスのデータを記述するプロパティ、クラスの動作を定義するメソッド、異なるクラスやオブジェクト間で通信するためのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-116">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="2ee9d-117">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-117">Properties and fields</span></span>

<span data-ttu-id="2ee9d-118">フィールドとプロパティは、オブジェクトに格納されている情報を表します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-118">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="2ee9d-119">フィールドは、適用されるアクセス修飾子に基づき、直接読み取ったり、設定したりできるという理由から変数と似ています。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-119">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="2ee9d-120">クラスのインスタンス内からアクセスできるフィールドを定義するには:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-120">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="2ee9d-121">プロパティには `get` と `set` というアクセサーがあります。これによって、値を設定する方法と値を返す方法を細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-121">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="2ee9d-122">C# では、プロパティ値を格納するプライベート フィールドを作成するか、自動実装プロパティを使用できます。自動実装プロパティでは、値を格納するフィールドが背後で自動的に作成され、プロパティ プロシージャの基本的なロジックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-122">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="2ee9d-123">自動実装プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-123">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="2ee9d-124">プロパティ値の読み取りと書き込みのために追加の操作を実行する必要がある場合は、プロパティ値を格納するフィールドを定義し、値を格納および取得する基本的なロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-124">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="2ee9d-125">ほとんどのプロパティには、プロパティ値の設定と取得を行うための両方のメソッドまたはプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-125">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="2ee9d-126">ただし、読み取り専用または書き込み専用のプロパティを作成して、プロパティの変更や読み取りを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-126">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="2ee9d-127">C# では、`get` プロパティ メソッドまたは `set` プロパティ メソッドを省略します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-127">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="2ee9d-128">ただし、自動実装プロパティを書き込み専用にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-128">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="2ee9d-129">読み取り専用の自動実装プロパティは、それが含まれるクラスのコンストラクターで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-129">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="2ee9d-130">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-130">For more information, see:</span></span>

- [<span data-ttu-id="2ee9d-131">get</span><span class="sxs-lookup"><span data-stu-id="2ee9d-131">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="2ee9d-132">set</span><span class="sxs-lookup"><span data-stu-id="2ee9d-132">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="2ee9d-133">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-133">Methods</span></span>

<span data-ttu-id="2ee9d-134">"*メソッド*" は、オブジェクトが実行できる処理です。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-134">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="2ee9d-135">クラスのメソッドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-135">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="2ee9d-136">クラスには、同じメソッドに対して、パラメーターの数やパラメーターの型が異なる複数の実装 ("*オーバーロード*") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-136">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="2ee9d-137">メソッドをオーバーロードするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-137">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="2ee9d-138">ほとんどの場合、メソッドはクラス定義内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-138">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="2ee9d-139">ただし、C# では、既存のクラスの実際の定義の外部にメソッドを追加できる "*拡張メソッド*" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-139">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="2ee9d-140">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-140">For more information, see:</span></span>

- [<span data-ttu-id="2ee9d-141">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-141">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="2ee9d-142">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-142">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="2ee9d-143">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="2ee9d-143">Constructors</span></span>

<span data-ttu-id="2ee9d-144">コンストラクターは、特定の型のオブジェクトを作成するときに自動的に実行されるクラス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-144">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="2ee9d-145">コンストラクターは、通常、新しいオブジェクトのデータ メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-145">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="2ee9d-146">コンストラクターは、クラスの作成時に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-146">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="2ee9d-147">また、コンストラクター内のコードは常に、クラス内の他のすべてのコードより先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-147">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="2ee9d-148">他のメソッドと同じように、コンストラクターにも複数のオーバーロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-148">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="2ee9d-149">クラスのコンストラクターを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-149">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="2ee9d-150">詳細については、「[コンストラクター](../classes-and-structs/constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-150">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="2ee9d-151">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="2ee9d-151">Finalizers</span></span>

<span data-ttu-id="2ee9d-152">ファイナライザーは、クラスのインスタンスを破棄するために使います。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-152">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="2ee9d-153">.NET Framework では、アプリケーション内のマネージド オブジェクトのメモリの割り当てと解放は、ガベージ コレクターによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-153">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="2ee9d-154">ただし、アプリケーションで作成されるアンマネージ リソースを適切にクリーンアップするために、ファイナライザーも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-154">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="2ee9d-155">1 つのクラスに定義できるファイナライザーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-155">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="2ee9d-156">.NET Framework のファイナライザーおよびガベージ コレクションについて詳しくは、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-156">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="2ee9d-157">イベント</span><span class="sxs-lookup"><span data-stu-id="2ee9d-157">Events</span></span>

<span data-ttu-id="2ee9d-158">クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-158">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="2ee9d-159">イベントを送信する (発生させる) クラスは "*パブリッシャー*" と呼ばれ、イベントを受信する (処理する) クラスは "*サブスクライバー*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-159">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="2ee9d-160">イベント、およびイベントの発生と処理の詳細については、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-160">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="2ee9d-161">クラスでイベントを宣言するには、[event](../../language-reference/keywords/event.md) キーワードを使います。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-161">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="2ee9d-162">イベントを発生させるには、イベント デリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-162">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="2ee9d-163">イベントをサブスクライブするには、`+=` 演算子を使用します。イベント サブスクリプションを解除するには、`-=` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-163">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="2ee9d-164">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="2ee9d-164">Nested classes</span></span>

<span data-ttu-id="2ee9d-165">別のクラス内で定義されているクラスを "*入れ子になったクラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-165">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="2ee9d-166">既定では、入れ子になったクラスはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-166">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="2ee9d-167">入れ子になったクラスのインスタンスを作成するには、コンテナー クラスの名前に続けて、ドットと入れ子になったクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-167">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="2ee9d-168">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="2ee9d-168">Access modifiers and access levels</span></span>

<span data-ttu-id="2ee9d-169">すべてのクラスおよびクラス メンバーでは、"*アクセス修飾子*" を使って、他のクラスに提供するアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-169">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="2ee9d-170">次のアクセス修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-170">The following access modifiers are available:</span></span>

|<span data-ttu-id="2ee9d-171">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="2ee9d-171">C# Modifier</span></span>|<span data-ttu-id="2ee9d-172">定義</span><span class="sxs-lookup"><span data-stu-id="2ee9d-172">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="2ee9d-173">public</span><span class="sxs-lookup"><span data-stu-id="2ee9d-173">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="2ee9d-174">この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-174">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="2ee9d-175">private</span><span class="sxs-lookup"><span data-stu-id="2ee9d-175">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="2ee9d-176">この型またはメンバーには、同じクラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-176">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="2ee9d-177">protected</span><span class="sxs-lookup"><span data-stu-id="2ee9d-177">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="2ee9d-178">この型またはメンバーには、同じクラスまたは派生クラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-178">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="2ee9d-179">internal</span><span class="sxs-lookup"><span data-stu-id="2ee9d-179">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="2ee9d-180">この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-180">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="2ee9d-181">protected internal</span><span class="sxs-lookup"><span data-stu-id="2ee9d-181">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="2ee9d-182">この型またはメンバーには、同じアセンブリ内の任意のコード、または別のアセンブリ内の任意の派生クラスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-182">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="2ee9d-183">private protected</span><span class="sxs-lookup"><span data-stu-id="2ee9d-183">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="2ee9d-184">この型またはメンバーには、基底クラス アセンブリ内の同じクラスまたは派生クラスのコードがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-184">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="2ee9d-185">詳細については、「[アクセス修飾子](../classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-185">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="2ee9d-186">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="2ee9d-186">Instantiating classes</span></span>

<span data-ttu-id="2ee9d-187">オブジェクトを作成するには、クラスをインスタンス化する (クラスのインスタンスを作成する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-187">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="2ee9d-188">クラスをインスタンス化した後は、インスタンスのプロパティやフィールドに値を割り当てたり、クラスのメソッドを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-188">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="2ee9d-189">クラスのインスタンス化のプロセスでプロパティに値を割り当てるには、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-189">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="2ee9d-190">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-190">For more information, see:</span></span>

- [<span data-ttu-id="2ee9d-191">new 演算子</span><span class="sxs-lookup"><span data-stu-id="2ee9d-191">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="2ee9d-192">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="2ee9d-192">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="2ee9d-193">静的クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="2ee9d-193">Static Classes and Members</span></span>

<span data-ttu-id="2ee9d-194">クラスの静的メンバーは、クラスのすべてのインスタンスで共有されるプロパティ、プロシージャ、またはフィールドです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-194">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="2ee9d-195">静的メンバーを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-195">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="2ee9d-196">静的メンバーにアクセスするには、クラスのオブジェクトを作成せずにクラスの名前を使います。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-196">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="2ee9d-197">C# の静的クラスには静的メンバーだけがあり、インスタンス化することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-197">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="2ee9d-198">また、静的メンバーから、非静的のプロパティ、フィールド、またはメソッドにアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-198">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="2ee9d-199">詳しくは、「[static](../../language-reference/keywords/static.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-199">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="2ee9d-200">匿名型</span><span class="sxs-lookup"><span data-stu-id="2ee9d-200">Anonymous types</span></span>

<span data-ttu-id="2ee9d-201">匿名型を使用すると、データ型のクラス定義を記述せずにオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-201">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="2ee9d-202">クラスは、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-202">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="2ee9d-203">このクラスには使用可能な名前がなく、オブジェクトの宣言時に指定したプロパティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-203">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="2ee9d-204">匿名型のインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-204">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="2ee9d-205">詳細については次を参照してください:[匿名型](../classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-205">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="2ee9d-206">継承</span><span class="sxs-lookup"><span data-stu-id="2ee9d-206">Inheritance</span></span>

<span data-ttu-id="2ee9d-207">継承を使用すると、他のクラスで定義されている動作を再利用、拡張、および変更する新しいクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-207">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="2ee9d-208">メンバーが継承される側のクラスを "*基底クラス*" と呼び、メンバーを継承する側のクラスを "*派生クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-208">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="2ee9d-209">ただし、C# のすべてのクラスは、.NET のクラス階層構造をサポートしてすべてのクラスに下位レベルのサービスを提供する <xref:System.Object> クラスを暗黙的に継承します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-209">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="2ee9d-210">C# は多重継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-210">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="2ee9d-211">つまり、派生クラスに対して指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-211">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="2ee9d-212">基底クラスを継承するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-212">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="2ee9d-213">既定では、すべてのクラスが継承可能になります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-213">By default all classes can be inherited.</span></span> <span data-ttu-id="2ee9d-214">ただし、クラスを基底クラスとして使用できないように指定したり、基底クラスとしてのみ使用できるクラスを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-214">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="2ee9d-215">クラスを基底クラスとして使用できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-215">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="2ee9d-216">クラスが基底クラスとしてのみ使用され、インスタンス化できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-216">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="2ee9d-217">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-217">For more information, see:</span></span>

- [<span data-ttu-id="2ee9d-218">sealed</span><span class="sxs-lookup"><span data-stu-id="2ee9d-218">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="2ee9d-219">abstract</span><span class="sxs-lookup"><span data-stu-id="2ee9d-219">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="2ee9d-220">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-220">Overriding Members</span></span>

<span data-ttu-id="2ee9d-221">既定では、派生クラスは基底クラスのすべてのメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-221">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="2ee9d-222">継承したメンバーの動作を変更する場合は、そのメンバーをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-222">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="2ee9d-223">つまり、派生クラスに、メソッド、プロパティ、またはイベントの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-223">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="2ee9d-224">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-224">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="2ee9d-225">C# の修飾子</span><span class="sxs-lookup"><span data-stu-id="2ee9d-225">C# Modifier</span></span>|<span data-ttu-id="2ee9d-226">定義</span><span class="sxs-lookup"><span data-stu-id="2ee9d-226">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="2ee9d-227">virtual</span><span class="sxs-lookup"><span data-stu-id="2ee9d-227">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="2ee9d-228">派生クラスでのクラス メンバーのオーバーライドを許可します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-228">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="2ee9d-229">override</span><span class="sxs-lookup"><span data-stu-id="2ee9d-229">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="2ee9d-230">基底クラスで定義されている仮想メンバー (オーバーライドできるメンバー) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-230">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="2ee9d-231">abstract</span><span class="sxs-lookup"><span data-stu-id="2ee9d-231">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="2ee9d-232">派生クラスでのクラス メンバーのオーバーライドを必須にします。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-232">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="2ee9d-233">new 修飾子</span><span class="sxs-lookup"><span data-stu-id="2ee9d-233">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="2ee9d-234">基底クラスから継承されたメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-234">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="2ee9d-235">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ee9d-235">Interfaces</span></span>

<span data-ttu-id="2ee9d-236">インターフェイスは、クラスと同様にプロパティ、メソッド、およびイベントのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-236">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="2ee9d-237">ただし、クラスとは異なり、インターフェイスは実装を提供しません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-237">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="2ee9d-238">インターフェイスはクラスによって実装され、クラスとは別のエンティティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-238">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="2ee9d-239">インターフェイスを実装するクラスは、そのインターフェイスのあらゆる機能を定義に従って厳密に実装する必要があります。この点で、インターフェイスはコントラクトを表しています。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-239">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="2ee9d-240">インターフェイスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-240">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="2ee9d-241">クラスにインターフェイスを実装するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-241">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="2ee9d-242">詳細については、プログラミング ガイド記事の[インターフェイス](../interfaces/index.md)に関する箇所と言語参照記事の [interface](../../language-reference/keywords/interface.md) というキーワードに関する箇所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-242">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="2ee9d-243">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="2ee9d-243">Generics</span></span>

<span data-ttu-id="2ee9d-244">.NET Framework のクラス、構造体、インターフェイス、およびメソッドは、格納または使用できるオブジェクトの型を定義する "*型パラメーター*" を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-244">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="2ee9d-245">ジェネリックの最も一般的な例として、コレクションがあります。コレクションには、その中に格納されるオブジェクトの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-245">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="2ee9d-246">ジェネリック クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-246">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="2ee9d-247">ジェネリック クラスのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-247">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="2ee9d-248">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-248">For more information, see:</span></span>

- [<span data-ttu-id="2ee9d-249">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="2ee9d-249">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="2ee9d-250">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="2ee9d-250">Generics</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="2ee9d-251">デリゲート</span><span class="sxs-lookup"><span data-stu-id="2ee9d-251">Delegates</span></span>

<span data-ttu-id="2ee9d-252">"*デリゲート*" は、メソッド シグネチャを定義する型であり、互換性のあるシグネチャを持つ任意のメソッドへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-252">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="2ee9d-253">メソッドは、デリゲートを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-253">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="2ee9d-254">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-254">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="2ee9d-255">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-255">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="2ee9d-256">デリゲートを使用したイベント処理について詳しくは、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-256">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="2ee9d-257">デリゲートを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-257">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="2ee9d-258">デリゲートで指定されたシグネチャに一致するメソッドへの参照を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-258">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="2ee9d-259">詳細については、プログラミング ガイド記事の[デリゲート](../delegates/index.md)に関する箇所と言語参照記事の [delegate](../../language-reference/builtin-types/reference-types.md) というキーワードに関する箇所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ee9d-259">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ee9d-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ee9d-260">See also</span></span>

- [<span data-ttu-id="2ee9d-261">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2ee9d-261">C# Programming Guide</span></span>](../index.md)
