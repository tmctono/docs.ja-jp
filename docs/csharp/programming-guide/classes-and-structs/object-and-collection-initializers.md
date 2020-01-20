---
title: オブジェクト初期化子とコレクション初期化子 - C# プログラミング ガイド
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 5565f37c9cfd8cb84c07f9ecc6f6c2edf8c66c61
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714750"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="6ed9f-102">オブジェクト初期化子とコレクション初期化子 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6ed9f-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="6ed9f-103">C# では、1 つの命令文でオブジェクトまたはコレクションをインスタンス化し、1 つのステートメントでメンバーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="6ed9f-104">オブジェクト初期化子</span><span class="sxs-lookup"><span data-stu-id="6ed9f-104">Object initializers</span></span>

<span data-ttu-id="6ed9f-105">オブジェクト初期化子を使用すると、オブジェクトの作成時にアクセスできるフィールドまたはプロパティに、コンストラクターを呼び出して代入ステートメントを使用しなくても、値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="6ed9f-106">オブジェクト初期化子の構文では、コンストラクターの引数を指定することも、引数 (およびかっこ構文) を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="6ed9f-107">以下の例では、名前付きの型である `Cat` でオブジェクト初期化子を使用する方法と、パラメーターなしのコンストラクターを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="6ed9f-108">`Cat` クラス内で自動実装プロパティが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="6ed9f-109">詳細については、「[自動実装プロパティ](auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
<span data-ttu-id="6ed9f-110">オブジェクト初期化子の構文では、インスタンスを作成できます。その後、新規作成されたオブジェクトは、割り当てられたプロパティと共に、割り当ての変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="6ed9f-111">C# 6 より、オブジェクト初期化子では、フィールドとプロパティを割り当てることに加え、インデクサーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="6ed9f-112">次の基底 `Matrix` クラスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="6ed9f-113">次のコードで単位行列を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="6ed9f-114">アクセス可能なセッターが含まれるアクセス可能なインデクサーを、引数の数や種類と関係なく、オブジェクト初期化子で式の 1 つとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="6ed9f-115">インデックス引数は代入の左側となり、値は式の右側となります。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="6ed9f-116">たとえば、`IndexersExample` に適切なインデクサーが指定されている場合、以下はすべて有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="6ed9f-117">上記のコードをコンパイルするには、`IndexersExample` 型に次のメンバーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="6ed9f-118">オブジェクト初期化子と匿名型</span><span class="sxs-lookup"><span data-stu-id="6ed9f-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="6ed9f-119">オブジェクト初期化子は、どのような場合にも使うことができますが、LINQ クエリ式で使うと特に有用です。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-119">Although object initializers can be used in any context, they are especially useful in LINQ query expressions.</span></span> <span data-ttu-id="6ed9f-120">クエリ式では、次の宣言に示すように、オブジェクト初期化子を使うことによってのみ初期化できる[匿名型](./anonymous-types.md)が頻繁に使われます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-120">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="6ed9f-121">匿名型を使うと、LINQ クエリ式の `select` 句によって元のシーケンスのオブジェクトを値と形状が元とは異なるオブジェクトに変換できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-121">Anonymous types enable the `select` clause in a LINQ query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="6ed9f-122">この方法は、シーケンス内の各オブジェクトの情報の一部のみを保存する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="6ed9f-123">次の例は、製品オブジェクト (`p`) に多くのフィールドおよびメソッドが含まれており、製品名および単価を含むオブジェクトのシーケンスを作成することにのみ関心があることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="6ed9f-124">このクエリが実行されると、`productInfos` 変数には、次の例に示す `foreach` ステートメントでアクセスできるオブジェクトのシーケンスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="6ed9f-125">作成される匿名型内の各オブジェクトには、2 つのパブリック プロパティがあります。これらのプロパティには、元のオブジェクトのプロパティまたはフィールドと同じ名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="6ed9f-126">匿名型を作成するときにフィールドの名前を変更することもできます。次の例では、フィールド `UnitPrice` の名前が `Price` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="6ed9f-127">コレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="6ed9f-127">Collection initializers</span></span>

<span data-ttu-id="6ed9f-128">コレクション初期化子を使うと、<xref:System.Collections.IEnumerable> を実装するコレクション型を初期化するときに 1 つ以上の要素の初期化子を指定でき、適切なシグネチャの `Add` をインスタンス メソッドまたは拡張メソッドとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="6ed9f-129">要素の初期化子は、単純な値、式またはオブジェクト初期化子です。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="6ed9f-130">コレクション初期化子を使用すると、呼び出しを複数回指定する必要がなくなります。コンパイラによって呼び出しが自動的に追加されるためです。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="6ed9f-131">2 つの単純なコレクション初期化子を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="6ed9f-132">次のコレクション初期化子は、前の例で定義されている `Cat` クラスのオブジェクトをオブジェクト初期化子を使用して初期化します。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="6ed9f-133">個々のオブジェクト初期化子は、かっこで囲まれ、コンマで区切られています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="6ed9f-134">コレクションの `Add` メソッドで許容されている場合、コレクション初期化子の要素として [null](../../language-reference/keywords/null.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="6ed9f-135">コレクションがインデックスを読み取り/書き込みできる場合は、インデックス付きの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="6ed9f-136">上記のサンプルの場合、<xref:System.Collections.Generic.Dictionary%602.Item(%600)> を呼び出して値を設定するコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="6ed9f-137">C# 6 以前は、次の構文を使用して、ディクショナリやその他の連想コンテナーを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-137">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="6ed9f-138">インデクサー構文の代わりに、括弧と代入によって 1 つのオブジェクトと複数の値が処理されていることにご注目ください。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="6ed9f-139">この初期化子の例では、<xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> を呼び出し、3 つの項目をディクショナリに追加しています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="6ed9f-140">連想コレクションを初期化するこれら 2 つの異なる方法には、コンパイラによって生成されるメソッド呼び出しにより、動作にわずかな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="6ed9f-141">いずれの場合も `Dictionary` クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="6ed9f-142">他の型の場合、パブリック API に基づいて、いずれかのみサポートされることがあります。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="6ed9f-143">使用例</span><span class="sxs-lookup"><span data-stu-id="6ed9f-143">Examples</span></span>

<span data-ttu-id="6ed9f-144">次の例では、オブジェクトの概念とコレクション初期化子の概念が組み合わさっています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="6ed9f-145">次の例のオブジェクトは <xref:System.Collections.IEnumerable> を実装します。このオブジェクトには `Add` メソッドと複数のパラメーターが含まれ、`Add` メソッドのシグネチャに対応するリスト項目ごとにコレクション初期化子と複数の要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="6ed9f-146">`Add` メソッドでは、次の例で示すように、`params` キーワードを使用して可変数個の引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="6ed9f-147">この例では、インデクサーのカスタム実装と、インデクサーを使用したコレクションの初期化を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ed9f-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="6ed9f-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ed9f-148">See also</span></span>

- [<span data-ttu-id="6ed9f-149">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6ed9f-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6ed9f-150">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="6ed9f-150">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="6ed9f-151">匿名型</span><span class="sxs-lookup"><span data-stu-id="6ed9f-151">Anonymous Types</span></span>](anonymous-types.md)
