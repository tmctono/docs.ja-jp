---
title: オブジェクト指向プログラミング
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 3739919273f4cdd285d519c414c542f1a82a16d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401305"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="c05e0-102">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c05e0-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="c05e0-103">Visual Basic では、カプセル化、継承、ポリモーフィズムなどのオブジェクト指向プログラミングを完全にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c05e0-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="c05e0-104">"*カプセル化*" とは、関連するプロパティ、メソッド、およびその他のメンバーのグループが 1 つの単位またはオブジェクトとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="c05e0-105">"*継承*" は、既存のクラスに基づいて新しいクラスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="c05e0-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="c05e0-106">"*ポリモーフィズム*" とは、同じプロパティまたはメソッドを異なる方法で実装している複数のクラスを、交換して使用できることです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="c05e0-107">このセクションでは、次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="c05e0-108">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c05e0-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="c05e0-109">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="c05e0-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="c05e0-110">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="c05e0-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="c05e0-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="c05e0-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="c05e0-112">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="c05e0-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="c05e0-113">デストラクター</span><span class="sxs-lookup"><span data-stu-id="c05e0-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="c05e0-114">Events</span><span class="sxs-lookup"><span data-stu-id="c05e0-114">Events</span></span>](#events)
    - [<span data-ttu-id="c05e0-115">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="c05e0-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="c05e0-116">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="c05e0-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="c05e0-117">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="c05e0-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="c05e0-118">共有クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="c05e0-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="c05e0-119">匿名型</span><span class="sxs-lookup"><span data-stu-id="c05e0-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="c05e0-120">継承</span><span class="sxs-lookup"><span data-stu-id="c05e0-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="c05e0-121">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c05e0-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="c05e0-122">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c05e0-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="c05e0-123">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="c05e0-123">Generics</span></span>](#generics)
- [<span data-ttu-id="c05e0-124">デリゲート</span><span class="sxs-lookup"><span data-stu-id="c05e0-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="c05e0-125">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c05e0-125">Classes and objects</span></span>

<span data-ttu-id="c05e0-126">"*クラス*" という用語と "*オブジェクト*" という用語は同じ意味で使われる場合がありますが、実際には、クラスはオブジェクトの "*型*" を表すのに対し、オブジェクトはクラスの使用可能な "*インスタンス*" です。</span><span class="sxs-lookup"><span data-stu-id="c05e0-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="c05e0-127">そのため、オブジェクトを作成する操作は "*インスタンス化*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="c05e0-128">設計図との対比を使って説明すると、クラスは設計図であり、オブジェクトはその設計図を基にした建築物です。</span><span class="sxs-lookup"><span data-stu-id="c05e0-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="c05e0-129">クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="c05e0-130">Visual Basic には、*構造体と呼*ばれるクラスの明るいバージョンも用意されており、オブジェクトの大きな配列を作成する必要があり、そのためにメモリをあまり消費したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c05e0-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="c05e0-131">構造体を定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="c05e0-132">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-132">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-133">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="c05e0-134">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="c05e0-135">クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="c05e0-135">Class members</span></span>

<span data-ttu-id="c05e0-136">各クラスには、さまざまな "*クラス メンバー*" を含めることができます。クラス メンバーには、クラスのデータを記述するプロパティ、クラスの動作を定義するメソッド、異なるクラスやオブジェクト間で通信するためのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="c05e0-137">プロパティとフィールド</span><span class="sxs-lookup"><span data-stu-id="c05e0-137">Properties and fields</span></span>

<span data-ttu-id="c05e0-138">フィールドとプロパティは、オブジェクトに格納されている情報を表します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="c05e0-139">フィールドは、直接読み取ったり設定したりできるので変数と似ています。</span><span class="sxs-lookup"><span data-stu-id="c05e0-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="c05e0-140">フィールドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="c05e0-141">プロパティには get プロシージャと set プロシージャがあり、これらを使用することで値の設定方法や戻り値をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="c05e0-142">Visual Basic では、プロパティ値を格納するためのプライベート フィールドを作成するか、またはこのフィールドを背後に自動的に作成し、プロパティ プロシージャの基本的なロジックを提供する、いわゆる自動実装プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="c05e0-143">自動実装プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="c05e0-144">プロパティ値の読み取りと書き込みのために追加の操作を実行する必要がある場合は、プロパティ値を格納するフィールドを定義し、値を格納および取得する基本的なロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="c05e0-145">ほとんどのプロパティには、プロパティ値の設定と取得を行うための両方のメソッドまたはプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="c05e0-146">ただし、読み取り専用または書き込み専用のプロパティを作成して、プロパティの変更や読み取りを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="c05e0-147">そのためには、Visual Basic では `ReadOnly` キーワードと `WriteOnly` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="c05e0-148">ただし、自動実装プロパティを読み取り専用または書き込み専用にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="c05e0-149">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-149">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-150">Property Statement</span><span class="sxs-lookup"><span data-stu-id="c05e0-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="c05e0-151">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="c05e0-152">ステートメントの設定</span><span class="sxs-lookup"><span data-stu-id="c05e0-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="c05e0-153">Readonly</span><span class="sxs-lookup"><span data-stu-id="c05e0-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="c05e0-154">書き込み専用</span><span class="sxs-lookup"><span data-stu-id="c05e0-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="c05e0-155">メソッド</span><span class="sxs-lookup"><span data-stu-id="c05e0-155">Methods</span></span>

 <span data-ttu-id="c05e0-156">"*メソッド*" は、オブジェクトが実行できる処理です。</span><span class="sxs-lookup"><span data-stu-id="c05e0-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="c05e0-157">Visual Basic には、メソッドを作成する方法が 2 つあります。メソッドが値を返さない場合は `Sub` ステートメントを使用し、メソッドが値を返す場合は `Function` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="c05e0-158">クラスのメソッドを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="c05e0-159">クラスには、同じメソッドに対して、パラメーターの数やパラメーターの型が異なる複数の実装 ("*オーバーロード*") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="c05e0-160">メソッドをオーバーロードするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="c05e0-161">ほとんどの場合、メソッドはクラス定義内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="c05e0-162">ただし、Visual Basic では、クラスの実際の定義の外部にある既存のクラスにメソッドを追加できる*拡張メソッド*もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c05e0-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="c05e0-163">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-163">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-164">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="c05e0-165">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c05e0-166">オーバー ロード</span><span class="sxs-lookup"><span data-stu-id="c05e0-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c05e0-167">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="c05e0-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="c05e0-168">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="c05e0-168">Constructors</span></span>

<span data-ttu-id="c05e0-169">コンストラクターは、特定の型のオブジェクトを作成するときに自動的に実行されるクラス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="c05e0-170">コンストラクターは、通常、新しいオブジェクトのデータ メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="c05e0-171">コンストラクターは、クラスの作成時に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="c05e0-172">また、コンストラクター内のコードは常に、クラス内の他のすべてのコードより先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="c05e0-173">他のメソッドと同じように、コンストラクターにも複数のオーバーロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="c05e0-174">クラスのコンストラクターを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="c05e0-175">詳細については、「[オブジェクトの有効期間 : オブジェクトの作成と破棄の方法](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="c05e0-176">デストラクター</span><span class="sxs-lookup"><span data-stu-id="c05e0-176">Destructors</span></span>

<span data-ttu-id="c05e0-177">デストラクターは、クラスのインスタンスを消滅させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="c05e0-178">.NET Framework では、アプリケーション内のマネージド オブジェクトのメモリの割り当てと解放は、ガベージ コレクターによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="c05e0-179">ただし、アプリケーションで作成されるアンマネージ リソースを適切にクリーンアップするために、デストラクターも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="c05e0-180">1 つのクラスに定義できるデストラクターは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="c05e0-181">.NET Framework のデストラクターおよびガベージ コレクションの詳細については、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="c05e0-182">events</span><span class="sxs-lookup"><span data-stu-id="c05e0-182">Events</span></span>

<span data-ttu-id="c05e0-183">クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="c05e0-184">イベントを送信 (または発生) するクラスは*パブリッシャー*と呼ばれ、イベントを受信 (または処理) するクラスは*サブスクライバ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="c05e0-185">イベント、およびイベントの発生と処理の詳細については、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="c05e0-186">イベントを宣言するには、[イベント ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="c05e0-187">イベントを発生させるには[、RaiseEvent ステートメント](../../../visual-basic/language-reference/statements/raiseevent-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="c05e0-188">宣言的な方法を使用してイベント ハンドラーを指定するには[、WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)ステートメントと[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)句を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="c05e0-189">イベントに関連付けられたイベント ハンドラを動的に追加、削除、および変更できるようにするには[、AddHandler ステートメント](../../../visual-basic/language-reference/statements/addhandler-statement.md)と[RemoveHandler ステートメント](../../../visual-basic/language-reference/statements/removehandler-statement.md)を[AddressOf 演算子](../../../visual-basic/language-reference/operators/addressof-operator.md)と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="c05e0-190">入れ子になったクラス</span><span class="sxs-lookup"><span data-stu-id="c05e0-190">Nested classes</span></span>

<span data-ttu-id="c05e0-191">別のクラス内で定義されているクラスを "*入れ子になったクラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="c05e0-192">既定では、入れ子になったクラスはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="c05e0-193">入れ子になったクラスのインスタンスを作成するには、コンテナー クラスの名前に続けて、ドットと入れ子になったクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="c05e0-194">アクセス修飾子とアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="c05e0-194">Access modifiers and access levels</span></span>

<span data-ttu-id="c05e0-195">すべてのクラスおよびクラス メンバーでは、"*アクセス修飾子*" を使って、他のクラスに提供するアクセス レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="c05e0-196">次のアクセス修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="c05e0-197">Visual Basic の修飾子</span><span class="sxs-lookup"><span data-stu-id="c05e0-197">Visual Basic Modifier</span></span>|<span data-ttu-id="c05e0-198">定義</span><span class="sxs-lookup"><span data-stu-id="c05e0-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="c05e0-199">公共</span><span class="sxs-lookup"><span data-stu-id="c05e0-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="c05e0-200">この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="c05e0-201">プライベート</span><span class="sxs-lookup"><span data-stu-id="c05e0-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="c05e0-202">この型またはメンバーには、同じクラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="c05e0-203">Protected</span><span class="sxs-lookup"><span data-stu-id="c05e0-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="c05e0-204">この型またはメンバーには、同じクラスまたは派生クラスのコードのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="c05e0-205">友人</span><span class="sxs-lookup"><span data-stu-id="c05e0-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="c05e0-206">この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="c05e0-207">この型またはメンバーには、同じアセンブリ内の任意のコード、または別のアセンブリ内の任意の派生クラスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="c05e0-208">詳細については、「 [Visual Basic のアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="c05e0-209">クラスのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="c05e0-209">Instantiating classes</span></span>

<span data-ttu-id="c05e0-210">オブジェクトを作成するには、クラスをインスタンス化する (クラスのインスタンスを作成する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="c05e0-211">クラスをインスタンス化した後は、インスタンスのプロパティやフィールドに値を割り当てたり、クラスのメソッドを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="c05e0-212">クラスのインスタンス化のプロセスでプロパティに値を割り当てるには、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="c05e0-213">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-213">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-214">新しいオペレータ</span><span class="sxs-lookup"><span data-stu-id="c05e0-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="c05e0-215">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="c05e0-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="c05e0-216">共有クラスとメンバー</span><span class="sxs-lookup"><span data-stu-id="c05e0-216">Shared classes and members</span></span>

 <span data-ttu-id="c05e0-217">クラスの共有メンバーは、クラスのすべてのインスタンスで共有されるプロパティ、プロシージャ、またはフィールドです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="c05e0-218">共有メンバーを定義するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c05e0-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="c05e0-219">共有メンバーにアクセスするには、このクラスのオブジェクトを作成せずにクラスの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="c05e0-220">Visual Basic の共有モジュールには共有メンバーのみがあり、インスタンス化することはできません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="c05e0-221">共有メンバは、共有されていないプロパティ、フィールド、またはメソッドにもアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="c05e0-222">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-222">For more information, see:</span></span>

- <span data-ttu-id="c05e0-223">[[共有](../../../visual-basic/language-reference/modifiers/shared.md)]</span><span class="sxs-lookup"><span data-stu-id="c05e0-223">[Shared](../../../visual-basic/language-reference/modifiers/shared.md)</span></span>
- [<span data-ttu-id="c05e0-224">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="c05e0-225">匿名型</span><span class="sxs-lookup"><span data-stu-id="c05e0-225">Anonymous types</span></span>

<span data-ttu-id="c05e0-226">匿名型を使用すると、データ型のクラス定義を記述せずにオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="c05e0-227">クラスは、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="c05e0-228">このクラスには使用可能な名前がなく、オブジェクトの宣言時に指定したプロパティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="c05e0-229">匿名型のインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="c05e0-230">詳細については、「[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="c05e0-231">継承</span><span class="sxs-lookup"><span data-stu-id="c05e0-231">Inheritance</span></span>

<span data-ttu-id="c05e0-232">継承を使用すると、他のクラスで定義されている動作を再利用、拡張、および変更する新しいクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="c05e0-233">メンバーが継承される側のクラスを "*基底クラス*" と呼び、メンバーを継承する側のクラスを "*派生クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="c05e0-234">ただし、Visual Basic のすべてのクラスは、.NET<xref:System.Object>クラス階層をサポートし、すべてのクラスに低レベルのサービスを提供するクラスから暗黙的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="c05e0-235">Visual Basic では、多重継承はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="c05e0-236">つまり、派生クラスに対して指定できる基底クラスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c05e0-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="c05e0-237">基底クラスを継承するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="c05e0-238">既定では、すべてのクラスが継承可能になります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-238">By default all classes can be inherited.</span></span> <span data-ttu-id="c05e0-239">ただし、クラスを基底クラスとして使用できないように指定したり、基底クラスとしてのみ使用できるクラスを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="c05e0-240">クラスを基底クラスとして使用できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="c05e0-241">クラスが基底クラスとしてのみ使用され、インスタンス化できないように指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="c05e0-242">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-242">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-243">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="c05e0-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="c05e0-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="c05e0-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="c05e0-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="c05e0-246">メンバーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c05e0-246">Overriding members</span></span>

<span data-ttu-id="c05e0-247">既定では、派生クラスは基底クラスのすべてのメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="c05e0-248">継承したメンバーの動作を変更する場合は、そのメンバーをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c05e0-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="c05e0-249">つまり、派生クラスに、メソッド、プロパティ、またはイベントの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="c05e0-250">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="c05e0-251">Visual Basic の修飾子</span><span class="sxs-lookup"><span data-stu-id="c05e0-251">Visual Basic Modifier</span></span>|<span data-ttu-id="c05e0-252">定義</span><span class="sxs-lookup"><span data-stu-id="c05e0-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="c05e0-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="c05e0-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="c05e0-254">派生クラスでのクラス メンバーのオーバーライドを許可します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="c05e0-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="c05e0-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="c05e0-256">基底クラスで定義されている仮想メンバー (オーバーライドできるメンバー) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c05e0-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="c05e0-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c05e0-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="c05e0-258">継承するクラスでのメンバーのオーバーライドを禁止します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="c05e0-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="c05e0-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="c05e0-260">派生クラスでのクラス メンバーのオーバーライドを必須にします。</span><span class="sxs-lookup"><span data-stu-id="c05e0-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="c05e0-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="c05e0-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="c05e0-262">基底クラスから継承されたメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="c05e0-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="c05e0-263">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c05e0-263">Interfaces</span></span>

<span data-ttu-id="c05e0-264">インターフェイスは、クラスと同様にプロパティ、メソッド、およびイベントのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="c05e0-265">ただし、クラスとは異なり、インターフェイスは実装を提供しません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="c05e0-266">インターフェイスはクラスによって実装され、クラスとは別のエンティティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="c05e0-267">インターフェイスを実装するクラスは、そのインターフェイスのあらゆる機能を定義に従って厳密に実装する必要があります。この点で、インターフェイスはコントラクトを表しています。</span><span class="sxs-lookup"><span data-stu-id="c05e0-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="c05e0-268">インターフェイスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="c05e0-269">クラスにインターフェイスを実装するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="c05e0-270">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-270">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-271">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c05e0-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="c05e0-272">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="c05e0-273">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="c05e0-274">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="c05e0-274">Generics</span></span>

<span data-ttu-id="c05e0-275">.NET のクラス、構造体、インターフェイス、およびメソッドには、格納または使用できるオブジェクトの型を定義する*型パラメーター*を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="c05e0-276">ジェネリックの最も一般的な例として、コレクションがあります。コレクションには、その中に格納されるオブジェクトの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="c05e0-277">ジェネリック クラスを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="c05e0-278">ジェネリック クラスのインスタンスを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="c05e0-279">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-279">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-280">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="c05e0-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="c05e0-281">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c05e0-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="c05e0-282">デリゲート</span><span class="sxs-lookup"><span data-stu-id="c05e0-282">Delegates</span></span>

 <span data-ttu-id="c05e0-283">"*デリゲート*" は、メソッド シグネチャを定義する型であり、互換性のあるシグネチャを持つ任意のメソッドへの参照を提供できます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="c05e0-284">メソッドは、デリゲートを使用して起動する (呼び出す) ことができます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="c05e0-285">デリゲートは、他のメソッドへの引数としてメソッドを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c05e0-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="c05e0-286">イベント ハンドラーは、デリゲートを介して呼び出されるメソッドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="c05e0-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="c05e0-287">デリゲートを使用したイベント処理について詳しくは、「[イベント](../../../standard/events/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="c05e0-288">デリゲートを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="c05e0-289">デリゲートで指定されたシグネチャに一致するメソッドへの参照を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c05e0-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="c05e0-290">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05e0-290">For more information, see:</span></span>

- [<span data-ttu-id="c05e0-291">デリゲート</span><span class="sxs-lookup"><span data-stu-id="c05e0-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="c05e0-292">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="c05e0-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="c05e0-293">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="c05e0-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="c05e0-294">関連項目</span><span class="sxs-lookup"><span data-stu-id="c05e0-294">See also</span></span>

- [<span data-ttu-id="c05e0-295">Visual Basic のプログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c05e0-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
