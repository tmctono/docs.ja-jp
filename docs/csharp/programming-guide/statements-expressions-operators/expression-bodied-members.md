---
title: 式形式のメンバー - C# プログラミング ガイド
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711988"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="b3248-102">式形式のメンバー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b3248-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="b3248-103">式本体の定義を使用すると、簡潔でわかりやすい形式でメンバーの実装を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3248-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="b3248-104">サポートされる任意のメンバー (メソッドやプロパティなど) に関するロジックが単一の式で構成される場合は、常に式本体の定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3248-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="b3248-105">式本体の定義には、次の一般的な構文があります。</span><span class="sxs-lookup"><span data-stu-id="b3248-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="b3248-106">この *expression* には有効な式を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3248-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="b3248-107">式本体の定義のサポートは、メソッドと読み取り専用プロパティのために C# 6 で導入され、C# 7.0 で拡張されました。</span><span class="sxs-lookup"><span data-stu-id="b3248-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="b3248-108">式本体の定義は、次の表の方メンバーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3248-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="b3248-109">メンバー</span><span class="sxs-lookup"><span data-stu-id="b3248-109">Member</span></span>  |<span data-ttu-id="b3248-110">サポートが開始されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b3248-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="b3248-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3248-111">Method</span></span>](#methods)  |<span data-ttu-id="b3248-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="b3248-112">C# 6</span></span> |
|[<span data-ttu-id="b3248-113">読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3248-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="b3248-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="b3248-114">C# 6</span></span>  |
|[<span data-ttu-id="b3248-115">Property</span><span class="sxs-lookup"><span data-stu-id="b3248-115">Property</span></span>](#properties)  |<span data-ttu-id="b3248-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b3248-116">C# 7.0</span></span> |
|[<span data-ttu-id="b3248-117">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="b3248-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="b3248-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b3248-118">C# 7.0</span></span> |
|[<span data-ttu-id="b3248-119">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="b3248-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="b3248-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b3248-120">C# 7.0</span></span> |
|[<span data-ttu-id="b3248-121">インデクサー</span><span class="sxs-lookup"><span data-stu-id="b3248-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="b3248-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b3248-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="b3248-123">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3248-123">Methods</span></span>

<span data-ttu-id="b3248-124">式形式のメソッドは、型がメソッドの戻り値の型と一致する値を返す単一の式、または、`void` を返すメソッドの場合は何らかの処理を実行する単一の式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b3248-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="b3248-125">たとえば、一般的に、<xref:System.Object.ToString%2A> メソッドをオーバーライドする型には、現在のオブジェクトの文字列形式を返す単一の式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3248-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="b3248-126">次の例では、式本体の定義を使用して <xref:System.Object.ToString%2A> メソッドをオーバーライドする `Person` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b3248-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="b3248-127">また、名前をコンソールに表示する `DisplayName` メソッドも定義します。</span><span class="sxs-lookup"><span data-stu-id="b3248-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="b3248-128">`ToString` 式本体の定義に `return` キーワードが使用されていない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="b3248-129">詳細については、「[メソッド (C# プログラミング ガイド)](../classes-and-structs/methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="b3248-130">読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3248-130">Read-only properties</span></span>

<span data-ttu-id="b3248-131">C# 6 以降では、式本体の定義を使用して読み取り専用プロパティを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="b3248-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="b3248-132">そのためには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3248-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="b3248-133">次の例では、プライベート `locationName` フィールドの値を返す式本体の定義として読み取り専用の `Name` プロパティを実装する `Location` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b3248-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="b3248-134">プロパティの詳細については、「[プロパティ (C# プログラミング ガイド)](../classes-and-structs/properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="b3248-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3248-135">Properties</span></span>

<span data-ttu-id="b3248-136">C# 7.0 以降では、式本体の定義を使用してプロパティ `get` と `set` アクセサーを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="b3248-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="b3248-137">これを実行する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="b3248-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="b3248-138">プロパティの詳細については、「[プロパティ (C# プログラミング ガイド)](../classes-and-structs/properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="b3248-139">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="b3248-139">Constructors</span></span>

<span data-ttu-id="b3248-140">一般的に、コンストラクターの式本体の定義は、コンストラクターの引数を処理したり、インスタンスの状態を初期化したりする単一の代入式またはメソッド呼び出しから構成されます。</span><span class="sxs-lookup"><span data-stu-id="b3248-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="b3248-141">次の例では、コンストラクターに *name* という名前の文字列パラメーターが 1 つある `Location` クラスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="b3248-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="b3248-142">式の本体の定義により `Name` プロパティに引数が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b3248-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="b3248-143">詳細については、「[コンストラクター (C# プログラミング ガイド)](../classes-and-structs/constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="b3248-144">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="b3248-144">Finalizers</span></span>

<span data-ttu-id="b3248-145">一般的に、ファイナライザーの式本体の定義には、アンマネージ リソースをリリースするステートメントなどのクリーンアップ ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3248-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="b3248-146">次の例では、式本体の定義を使用して、ファイナライザーが呼び出されたことを示すファイナライザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b3248-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="b3248-147">詳細については、「[ファイナライザー (C# プログラミング ガイド)](../classes-and-structs/destructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="b3248-148">インデクサー</span><span class="sxs-lookup"><span data-stu-id="b3248-148">Indexers</span></span>

<span data-ttu-id="b3248-149">プロパティと同様に、`get` アクセサーが値を返す単一のステートメントで構成される場合、または `set` アクセサーがシンプルな代入を実行する場合、インデクサーの `get` と `set` アクセサーは、式本体の定義で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b3248-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="b3248-150">次の例では、`Sports` というクラスを定義します。このクラスには、複数のスポーツ名を含む内部 <xref:System.String> 配列があります。</span><span class="sxs-lookup"><span data-stu-id="b3248-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="b3248-151">インデクサーの `get` および `set` アクセサーはいずれも、式本体の定義として実装されます。</span><span class="sxs-lookup"><span data-stu-id="b3248-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="b3248-152">詳細については、「[インデクサー (C# プログラミング ガイド)](../indexers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3248-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
