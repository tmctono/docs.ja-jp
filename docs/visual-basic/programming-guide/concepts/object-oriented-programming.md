---
title: オブジェクト指向プログラミング
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: f7e222cde8ce80d4c52cc8b4b111c576eb4041b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413194"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="70932-102">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70932-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="70932-103">Visual Basic は、カプセル化、継承、ポリモーフィズムなど、オブジェクト指向プログラミングを完全にサポートします。</span><span class="sxs-lookup"><span data-stu-id="70932-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="70932-104">"*カプセル化*" とは、関連するプロパティ、メソッド、およびその他のメンバーのグループが 1 つの単位またはオブジェクトとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="70932-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="70932-105">"*継承*" は、既存のクラスに基づいて新しいクラスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="70932-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="70932-106">"*ポリモーフィズム*" とは、同じプロパティまたはメソッドを異なる方法で実装している複数のクラスを、交換して使用できることです。</span><span class="sxs-lookup"><span data-stu-id="70932-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="70932-107">このセクションでは、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="70932-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="70932-108">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="70932-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="70932-109">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="70932-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="70932-110">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="70932-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="70932-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="70932-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="70932-112">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="70932-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="70932-113">デストラクター</span><span class="sxs-lookup"><span data-stu-id="70932-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="70932-114">イベント</span><span class="sxs-lookup"><span data-stu-id="70932-114">Events</span></span>](#events)
    - [<span data-ttu-id="70932-115">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="70932-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="70932-116">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="70932-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="70932-117">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="70932-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="70932-118">共有クラスおよびメンバー</span><span class="sxs-lookup"><span data-stu-id="70932-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="70932-119">匿名型</span><span class="sxs-lookup"><span data-stu-id="70932-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="70932-120">継承</span><span class="sxs-lookup"><span data-stu-id="70932-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="70932-121">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="70932-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="70932-122">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70932-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="70932-123">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="70932-123">Generics</span></span>](#generics)
- [<span data-ttu-id="70932-124">デリゲート</span><span class="sxs-lookup"><span data-stu-id="70932-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="70932-125">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="70932-125">Classes and objects</span></span>

<span data-ttu-id="70932-126">"*クラス*" という用語と "*オブジェクト*" という用語は同じ意味で使われる場合がありますが、実際には、クラスはオブジェクトの "*型*" を表すのに対し、オブジェクトはクラスの使用可能な "*インスタンス*" です。</span><span class="sxs-lookup"><span data-stu-id="70932-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="70932-127">そのため、オブジェクトを作成する操作は "*インスタンス化*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="70932-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="70932-128">設計図との対比を使って説明すると、クラスは設計図であり、オブジェクトはその設計図を基にした建築物です。</span><span class="sxs-lookup"><span data-stu-id="70932-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="70932-129">クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="70932-130">Visual Basic には、"*構造体*" と呼ばれる軽量バージョンのクラスも用意されています。構造体は、大きいオブジェクト配列を作成する必要があり、その配列に使用されるメモリの量を抑えたい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="70932-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="70932-131">構造体を定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="70932-132">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-132">For more information, see:</span></span>

- [<span data-ttu-id="70932-133">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-133">Class Statement</span></span>](../../language-reference/statements/class-statement.md)
- [<span data-ttu-id="70932-134">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-134">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="70932-135">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="70932-135">Class members</span></span>

<span data-ttu-id="70932-136">各クラスには、さまざまな "*クラス メンバー*" を含めることができます。クラス メンバーには、クラスのデータを記述するプロパティ、クラスの動作を定義するメソッド、異なるクラスやオブジェクト間で通信するためのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="70932-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="70932-137">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="70932-137">Properties and fields</span></span>

<span data-ttu-id="70932-138">フィールドとプロパティは、オブジェクトに格納されている情報を表します。</span><span class="sxs-lookup"><span data-stu-id="70932-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="70932-139">フィールドは、直接読み取ったり設定したりできるので変数と似ています。</span><span class="sxs-lookup"><span data-stu-id="70932-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="70932-140">フィールドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="70932-141">プロパティには get プロシージャと set プロシージャがあり、これらを使用することで値の設定方法や戻り値をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="70932-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="70932-142">Visual Basic では、プロパティ値を格納するプライベート フィールドを作成するか、または自動実装プロパティと呼ばれる手法を使用できます。自動実装プロパティでは、値を格納するフィールドが背後で自動的に作成され、プロパティ プロシージャの基本的なロジックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="70932-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="70932-143">自動実装プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="70932-144">プロパティ値の読み取りと書き込みのために追加の操作を実行する必要がある場合は、プロパティ値を格納するフィールドを定義し、値を格納および取得する基本的なロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="70932-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="70932-145">ほとんどのプロパティには、プロパティ値の設定と取得を行うための両方のメソッドまたはプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="70932-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="70932-146">ただし、読み取り専用または書き込み専用のプロパティを作成して、プロパティの変更や読み取りを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="70932-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="70932-147">そのためには、Visual Basic では `ReadOnly` キーワードと `WriteOnly` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="70932-148">ただし、自動実装プロパティを読み取り専用または書き込み専用にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="70932-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="70932-149">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-149">For more information, see:</span></span>

- [<span data-ttu-id="70932-150">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-150">Property Statement</span></span>](../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="70932-151">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-151">Get Statement</span></span>](../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="70932-152">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-152">Set Statement</span></span>](../../language-reference/statements/set-statement.md)
- [<span data-ttu-id="70932-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="70932-153">ReadOnly</span></span>](../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="70932-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="70932-154">WriteOnly</span></span>](../../language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="70932-155">メソッド</span><span class="sxs-lookup"><span data-stu-id="70932-155">Methods</span></span>

 <span data-ttu-id="70932-156">"*メソッド*" は、オブジェクトが実行できる処理です。</span><span class="sxs-lookup"><span data-stu-id="70932-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="70932-157">Visual Basic には、メソッドを作成する方法が 2 つあります。メソッドが値を返さない場合は `Sub` ステートメントを使用し、メソッドが値を返す場合は `Function` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="70932-158">クラスのメソッドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="70932-159">クラスには、同じメソッドに対して、パラメーターの数やパラメーターの型が異なる複数の実装 ("*オーバーロード*") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="70932-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="70932-160">メソッドをオーバーロードするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="70932-161">ほとんどの場合、メソッドはクラス定義内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="70932-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="70932-162">ただし、Visual Basic では、既存のクラスの実際の定義の外部にメソッドを追加できる "*拡張メソッド*" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="70932-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="70932-163">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-163">For more information, see:</span></span>

- [<span data-ttu-id="70932-164">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-164">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="70932-165">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-165">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="70932-166">Overloads</span><span class="sxs-lookup"><span data-stu-id="70932-166">Overloads</span></span>](../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="70932-167">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="70932-167">Extension Methods</span></span>](../language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="70932-168">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="70932-168">Constructors</span></span>

<span data-ttu-id="70932-169">コンストラクターは、特定の型のオブジェクトを作成するときに自動的に実行されるクラス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="70932-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="70932-170">コンストラクターは、通常、新しいオブジェクトのデータ メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="70932-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="70932-171">コンストラクターは、クラスの作成時に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="70932-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="70932-172">また、コンストラクター内のコードは常に、クラス内の他のすべてのコードより先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="70932-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="70932-173">他のメソッドと同じように、コンストラクターにも複数のオーバーロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="70932-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="70932-174">クラスのコンストラクターを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="70932-175">詳細については次を参照してください:[オブジェクトの有効期間: オブジェクトの作成と破棄](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="70932-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="70932-176">デストラクター</span><span class="sxs-lookup"><span data-stu-id="70932-176">Destructors</span></span>

<span data-ttu-id="70932-177">デストラクターは、クラスのインスタンスを消滅させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="70932-178">.NET Framework では、アプリケーション内のマネージド オブジェクトのメモリの割り当てと解放は、ガベージ コレクターによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="70932-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="70932-179">ただし、アプリケーションで作成されるアンマネージ リソースを適切にクリーンアップするために、デストラクターも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="70932-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="70932-180">1 つのクラスに定義できるデストラクターは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="70932-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="70932-181">.NET Framework のデストラクターおよびガベージ コレクションの詳細については、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70932-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="70932-182">イベント</span><span class="sxs-lookup"><span data-stu-id="70932-182">Events</span></span>

<span data-ttu-id="70932-183">クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="70932-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="70932-184">イベントを送信する (発生させる) クラスは "*パブリッシャー*" と呼ばれ、イベントを受信する (処理する) クラスは "*サブスクライバー*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="70932-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="70932-185">イベント、およびイベントの発生と処理の詳細については、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70932-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="70932-186">イベントを宣言するには、[Event ステートメント](../../language-reference/statements/event-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-186">To declare events, use the [Event Statement](../../language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="70932-187">イベントを発生させるには、[RaiseEvent ステートメント](../../language-reference/statements/raiseevent-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-187">To raise events, use the [RaiseEvent Statement](../../language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="70932-188">宣言によってイベント ハンドラーを指定するには、[WithEvents](../../language-reference/modifiers/withevents.md) ステートメントと [Handles](../../language-reference/statements/handles-clause.md) 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-188">To specify event handlers using a declarative way, use the [WithEvents](../../language-reference/modifiers/withevents.md) statement and the [Handles](../../language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="70932-189">イベントに関連付けるイベント ハンドラーを動的に追加、削除、変更できるようにするには、[AddHandler ステートメント](../../language-reference/statements/addhandler-statement.md)と [RemoveHandler ステートメント](../../language-reference/statements/removehandler-statement.md)に [AddressOf 演算子](../../language-reference/operators/addressof-operator.md)を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="70932-190">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="70932-190">Nested classes</span></span>

<span data-ttu-id="70932-191">別のクラス内で定義されているクラスを "*入れ子になったクラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="70932-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="70932-192">既定では、入れ子になったクラスはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="70932-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="70932-193">入れ子になったクラスのインスタンスを作成するには、コンテナー クラスの名前に続けて、ドットと入れ子になったクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="70932-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="70932-194">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="70932-194">Access modifiers and access levels</span></span>

<span data-ttu-id="70932-195">すべてのクラスおよびクラス メンバーでは、"*アクセス修飾子*" を使って、他のクラスに提供するアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="70932-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="70932-196">次のアクセス修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="70932-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="70932-197">Visual Basic の修飾子</span><span class="sxs-lookup"><span data-stu-id="70932-197">Visual Basic Modifier</span></span>|<span data-ttu-id="70932-198">定義</span><span class="sxs-lookup"><span data-stu-id="70932-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="70932-199">Public</span><span class="sxs-lookup"><span data-stu-id="70932-199">Public</span></span>](../../language-reference/modifiers/public.md)|<span data-ttu-id="70932-200">この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70932-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="70932-201">Private</span><span class="sxs-lookup"><span data-stu-id="70932-201">Private</span></span>](../../language-reference/modifiers/private.md)|<span data-ttu-id="70932-202">この型またはメンバーには、同じクラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70932-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="70932-203">Protected</span><span class="sxs-lookup"><span data-stu-id="70932-203">Protected</span></span>](../../language-reference/modifiers/protected.md)|<span data-ttu-id="70932-204">この型またはメンバーには、同じクラスまたは派生クラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70932-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="70932-205">Friend</span><span class="sxs-lookup"><span data-stu-id="70932-205">Friend</span></span>](../../language-reference/modifiers/friend.md)|<span data-ttu-id="70932-206">この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="70932-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="70932-207">この型またはメンバーには、同じアセンブリ内の任意のコード、または別のアセンブリ内の任意の派生クラスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70932-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="70932-208">詳しくは、「[Visual Basic でのアクセス レベル](../language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70932-208">For more information, see [Access levels in Visual Basic](../language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="70932-209">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="70932-209">Instantiating classes</span></span>

<span data-ttu-id="70932-210">オブジェクトを作成するには、クラスをインスタンス化する (クラスのインスタンスを作成する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="70932-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="70932-211">クラスをインスタンス化した後は、インスタンスのプロパティやフィールドに値を割り当てたり、クラスのメソッドを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="70932-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="70932-212">クラスのインスタンス化のプロセスでプロパティに値を割り当てるには、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="70932-213">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-213">For more information, see:</span></span>

- [<span data-ttu-id="70932-214">New 演算子</span><span class="sxs-lookup"><span data-stu-id="70932-214">New Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="70932-215">オブジェクト初期化子: 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="70932-215">Object Initializers: Named and Anonymous Types</span></span>](../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="70932-216">共有クラスおよびメンバー</span><span class="sxs-lookup"><span data-stu-id="70932-216">Shared classes and members</span></span>

 <span data-ttu-id="70932-217">クラスの共有メンバーは、クラスのすべてのインスタンスで共有されるプロパティ、プロシージャ、またはフィールドです。</span><span class="sxs-lookup"><span data-stu-id="70932-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="70932-218">共有メンバーを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="70932-219">共有メンバーにアクセスするには、クラスのオブジェクトを作成せずにクラスの名前を使います。</span><span class="sxs-lookup"><span data-stu-id="70932-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="70932-220">Visual Basic の共有モジュールには共有メンバーだけが含まれ、これらをインスタンス化することはできません。</span><span class="sxs-lookup"><span data-stu-id="70932-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="70932-221">また、共有メンバーから、非共有のプロパティ、フィールド、またはメソッドにアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="70932-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="70932-222">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-222">For more information, see:</span></span>

- [<span data-ttu-id="70932-223">Shared</span><span class="sxs-lookup"><span data-stu-id="70932-223">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="70932-224">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-224">Module Statement</span></span>](../../language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="70932-225">匿名型</span><span class="sxs-lookup"><span data-stu-id="70932-225">Anonymous types</span></span>

<span data-ttu-id="70932-226">匿名型を使用すると、データ型のクラス定義を記述せずにオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="70932-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="70932-227">クラスは、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="70932-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="70932-228">このクラスには使用可能な名前がなく、オブジェクトの宣言時に指定したプロパティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="70932-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="70932-229">匿名型のインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="70932-230">詳細については次を参照してください:[匿名型](../language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="70932-230">For more information, see: [Anonymous Types](../language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="70932-231">継承</span><span class="sxs-lookup"><span data-stu-id="70932-231">Inheritance</span></span>

<span data-ttu-id="70932-232">継承を使用すると、他のクラスで定義されている動作を再利用、拡張、および変更する新しいクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="70932-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="70932-233">メンバーが継承される側のクラスを "*基底クラス*" と呼び、メンバーを継承する側のクラスを "*派生クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="70932-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="70932-234">ただし、Visual Basic のすべてのクラスは、.NET のクラス階層構造をサポートしてすべてのクラスに下位レベルのサービスを提供する <xref:System.Object> クラスを暗黙的に継承します。</span><span class="sxs-lookup"><span data-stu-id="70932-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="70932-235">Visual Basic は多重継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="70932-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="70932-236">つまり、派生クラスに対して指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="70932-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="70932-237">基底クラスを継承するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="70932-238">既定では、すべてのクラスが継承可能になります。</span><span class="sxs-lookup"><span data-stu-id="70932-238">By default all classes can be inherited.</span></span> <span data-ttu-id="70932-239">ただし、クラスを基底クラスとして使用できないように指定したり、基底クラスとしてのみ使用できるクラスを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="70932-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="70932-240">クラスを基底クラスとして使用できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="70932-241">クラスが基底クラスとしてのみ使用され、インスタンス化できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="70932-242">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-242">For more information, see:</span></span>

- [<span data-ttu-id="70932-243">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-243">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="70932-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="70932-244">NotInheritable</span></span>](../../language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="70932-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="70932-245">MustInherit</span></span>](../../language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="70932-246">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="70932-246">Overriding members</span></span>

<span data-ttu-id="70932-247">既定では、派生クラスは基底クラスのすべてのメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="70932-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="70932-248">継承したメンバーの動作を変更する場合は、そのメンバーをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70932-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="70932-249">つまり、派生クラスに、メソッド、プロパティ、またはイベントの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="70932-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="70932-250">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="70932-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="70932-251">Visual Basic の修飾子</span><span class="sxs-lookup"><span data-stu-id="70932-251">Visual Basic Modifier</span></span>|<span data-ttu-id="70932-252">定義</span><span class="sxs-lookup"><span data-stu-id="70932-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="70932-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="70932-253">Overridable</span></span>](../../language-reference/modifiers/overridable.md)|<span data-ttu-id="70932-254">派生クラスでのクラス メンバーのオーバーライドを許可します。</span><span class="sxs-lookup"><span data-stu-id="70932-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="70932-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="70932-255">Overrides</span></span>](../../language-reference/modifiers/overrides.md)|<span data-ttu-id="70932-256">基底クラスで定義されている仮想メンバー (オーバーライドできるメンバー) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="70932-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="70932-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="70932-257">NotOverridable</span></span>](../../language-reference/modifiers/notoverridable.md)|<span data-ttu-id="70932-258">継承するクラスでのメンバーのオーバーライドを禁止します。</span><span class="sxs-lookup"><span data-stu-id="70932-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="70932-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="70932-259">MustOverride</span></span>](../../language-reference/modifiers/mustoverride.md)|<span data-ttu-id="70932-260">派生クラスでのクラス メンバーのオーバーライドを必須にします。</span><span class="sxs-lookup"><span data-stu-id="70932-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="70932-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="70932-261">Shadows</span></span>](../../language-reference/modifiers/shadows.md)|<span data-ttu-id="70932-262">基底クラスから継承されたメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="70932-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="70932-263">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70932-263">Interfaces</span></span>

<span data-ttu-id="70932-264">インターフェイスは、クラスと同様にプロパティ、メソッド、およびイベントのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="70932-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="70932-265">ただし、クラスとは異なり、インターフェイスは実装を提供しません。</span><span class="sxs-lookup"><span data-stu-id="70932-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="70932-266">インターフェイスはクラスによって実装され、クラスとは別のエンティティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="70932-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="70932-267">インターフェイスを実装するクラスは、そのインターフェイスのあらゆる機能を定義に従って厳密に実装する必要があります。この点で、インターフェイスはコントラクトを表しています。</span><span class="sxs-lookup"><span data-stu-id="70932-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="70932-268">インターフェイスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="70932-269">クラスにインターフェイスを実装するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="70932-270">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-270">For more information, see:</span></span>

- [<span data-ttu-id="70932-271">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70932-271">Interfaces</span></span>](../language-features/interfaces/index.md)
- [<span data-ttu-id="70932-272">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-272">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)
- [<span data-ttu-id="70932-273">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-273">Implements Statement</span></span>](../../language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="70932-274">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="70932-274">Generics</span></span>

<span data-ttu-id="70932-275">.NET のクラス、構造体、インターフェイス、およびメソッドは、格納または使用できるオブジェクトの型を定義する "*型パラメーター*" を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="70932-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="70932-276">ジェネリックの最も一般的な例として、コレクションがあります。コレクションには、その中に格納されるオブジェクトの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="70932-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="70932-277">ジェネリック クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="70932-278">ジェネリック クラスのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="70932-279">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-279">For more information, see:</span></span>

- [<span data-ttu-id="70932-280">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="70932-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="70932-281">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70932-281">Generic Types in Visual Basic</span></span>](../language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="70932-282">デリゲート</span><span class="sxs-lookup"><span data-stu-id="70932-282">Delegates</span></span>

 <span data-ttu-id="70932-283">"*デリゲート*" は、メソッド シグネチャを定義する型であり、互換性のあるシグネチャを持つ任意のメソッドへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="70932-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="70932-284">メソッドは、デリゲートを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="70932-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="70932-285">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="70932-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="70932-286">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="70932-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="70932-287">デリゲートを使用したイベント処理について詳しくは、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70932-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="70932-288">デリゲートを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="70932-289">デリゲートで指定されたシグネチャに一致するメソッドへの参照を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70932-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="70932-290">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="70932-290">For more information, see:</span></span>

- [<span data-ttu-id="70932-291">デリゲート</span><span class="sxs-lookup"><span data-stu-id="70932-291">Delegates</span></span>](../language-features/delegates/index.md)
- [<span data-ttu-id="70932-292">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="70932-292">Delegate Statement</span></span>](../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="70932-293">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="70932-293">AddressOf Operator</span></span>](../../language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="70932-294">関連項目</span><span class="sxs-lookup"><span data-stu-id="70932-294">See also</span></span>

- [<span data-ttu-id="70932-295">Visual Basic プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="70932-295">Visual Basic Programming Guide</span></span>](../index.md)
