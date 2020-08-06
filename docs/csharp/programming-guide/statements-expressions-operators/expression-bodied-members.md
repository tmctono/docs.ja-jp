---
title: 式形式のメンバー - C# プログラミング ガイド
description: 式形式のメンバーについて説明します。 プロパティ、コンストラクター、ファイナライザーなどの式本体の定義を使用するコード例を参照してください。
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: e68e96e4aa3ff6a64590459a7197da1833e1a275
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381659"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="76283-104">式形式のメンバー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="76283-104">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="76283-105">式本体の定義を使用すると、簡潔でわかりやすい形式でメンバーの実装を指定できます。</span><span class="sxs-lookup"><span data-stu-id="76283-105">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="76283-106">サポートされる任意のメンバー (メソッドやプロパティなど) に関するロジックが単一の式で構成される場合は、常に式本体の定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="76283-106">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="76283-107">式本体の定義には、次の一般的な構文があります。</span><span class="sxs-lookup"><span data-stu-id="76283-107">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="76283-108">この *expression* には有効な式を指定します。</span><span class="sxs-lookup"><span data-stu-id="76283-108">where *expression* is a valid expression.</span></span>

<span data-ttu-id="76283-109">式本体の定義のサポートは、メソッドと読み取り専用プロパティのために C# 6 で導入され、C# 7.0 で拡張されました。</span><span class="sxs-lookup"><span data-stu-id="76283-109">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="76283-110">式本体の定義は、次の表の方メンバーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="76283-110">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="76283-111">メンバー</span><span class="sxs-lookup"><span data-stu-id="76283-111">Member</span></span>  |<span data-ttu-id="76283-112">サポートが開始されたバージョン</span><span class="sxs-lookup"><span data-stu-id="76283-112">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="76283-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="76283-113">Method</span></span>](#methods)  |<span data-ttu-id="76283-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="76283-114">C# 6</span></span> |
|[<span data-ttu-id="76283-115">読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="76283-115">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="76283-116">C# 6</span><span class="sxs-lookup"><span data-stu-id="76283-116">C# 6</span></span>  |
|[<span data-ttu-id="76283-117">Property</span><span class="sxs-lookup"><span data-stu-id="76283-117">Property</span></span>](#properties)  |<span data-ttu-id="76283-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="76283-118">C# 7.0</span></span> |
|[<span data-ttu-id="76283-119">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="76283-119">Constructor</span></span>](#constructors)   |<span data-ttu-id="76283-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="76283-120">C# 7.0</span></span> |
|[<span data-ttu-id="76283-121">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="76283-121">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="76283-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="76283-122">C# 7.0</span></span> |
|[<span data-ttu-id="76283-123">インデクサー</span><span class="sxs-lookup"><span data-stu-id="76283-123">Indexer</span></span>](#indexers)       |<span data-ttu-id="76283-124">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="76283-124">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="76283-125">メソッド</span><span class="sxs-lookup"><span data-stu-id="76283-125">Methods</span></span>

<span data-ttu-id="76283-126">式形式のメソッドは、型がメソッドの戻り値の型と一致する値を返す単一の式、または、`void` を返すメソッドの場合は何らかの処理を実行する単一の式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76283-126">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="76283-127">たとえば、一般的に、<xref:System.Object.ToString%2A> メソッドをオーバーライドする型には、現在のオブジェクトの文字列形式を返す単一の式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76283-127">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="76283-128">次の例では、式本体の定義を使用して <xref:System.Object.ToString%2A> メソッドをオーバーライドする `Person` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="76283-128">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="76283-129">また、名前をコンソールに表示する `DisplayName` メソッドも定義します。</span><span class="sxs-lookup"><span data-stu-id="76283-129">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="76283-130">`ToString` 式本体の定義に `return` キーワードが使用されていない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="76283-130">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="76283-131">詳細については、「[メソッド (C# プログラミング ガイド)](../classes-and-structs/methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-131">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="76283-132">読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="76283-132">Read-only properties</span></span>

<span data-ttu-id="76283-133">C# 6 以降では、式本体の定義を使用して読み取り専用プロパティを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="76283-133">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="76283-134">そのためには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76283-134">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="76283-135">次の例では、プライベート `locationName` フィールドの値を返す式本体の定義として読み取り専用の `Name` プロパティを実装する `Location` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="76283-135">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="76283-136">プロパティの詳細については、「[プロパティ (C# プログラミング ガイド)](../classes-and-structs/properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-136">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="76283-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="76283-137">Properties</span></span>

<span data-ttu-id="76283-138">C# 7.0 以降では、式本体の定義を使用してプロパティ `get` と `set` アクセサーを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="76283-138">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="76283-139">これを実行する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="76283-139">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="76283-140">プロパティの詳細については、「[プロパティ (C# プログラミング ガイド)](../classes-and-structs/properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-140">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="76283-141">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="76283-141">Constructors</span></span>

<span data-ttu-id="76283-142">一般的に、コンストラクターの式本体の定義は、コンストラクターの引数を処理したり、インスタンスの状態を初期化したりする単一の代入式またはメソッド呼び出しから構成されます。</span><span class="sxs-lookup"><span data-stu-id="76283-142">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="76283-143">次の例では、コンストラクターに *name* という名前の文字列パラメーターが 1 つある `Location` クラスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="76283-143">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="76283-144">式の本体の定義により `Name` プロパティに引数が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="76283-144">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="76283-145">詳細については、「[コンストラクター (C# プログラミング ガイド)](../classes-and-structs/constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-145">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="76283-146">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="76283-146">Finalizers</span></span>

<span data-ttu-id="76283-147">一般的に、ファイナライザーの式本体の定義には、アンマネージ リソースをリリースするステートメントなどのクリーンアップ ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="76283-147">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="76283-148">次の例では、式本体の定義を使用して、ファイナライザーが呼び出されたことを示すファイナライザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="76283-148">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="76283-149">詳細については、「[ファイナライザー (C# プログラミング ガイド)](../classes-and-structs/destructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-149">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="76283-150">インデクサー</span><span class="sxs-lookup"><span data-stu-id="76283-150">Indexers</span></span>

<span data-ttu-id="76283-151">プロパティと同様に、`get` アクセサーが値を返す単一のステートメントで構成される場合、または `set` アクセサーがシンプルな代入を実行する場合、インデクサーの `get` と `set` アクセサーは、式本体の定義で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76283-151">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="76283-152">次の例では、`Sports` というクラスを定義します。このクラスには、複数のスポーツ名を含む内部 <xref:System.String> 配列があります。</span><span class="sxs-lookup"><span data-stu-id="76283-152">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="76283-153">インデクサーの `get` および `set` アクセサーはいずれも、式本体の定義として実装されます。</span><span class="sxs-lookup"><span data-stu-id="76283-153">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="76283-154">詳細については、「[インデクサー (C# プログラミング ガイド)](../indexers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76283-154">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
