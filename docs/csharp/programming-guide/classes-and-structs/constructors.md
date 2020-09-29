---
title: コンストラクター - C# プログラミング ガイド
description: C# のコンストラクターは、クラスまたは構造体が作成されたときに呼び出されます。 コンストラクターを使用して既定値を設定し、インスタンス化を制限し、柔軟で読みやすいコードを記述します。
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: e26c5100691bb313e0b68e1d1dab4209bd5d5da9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174317"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="1d96f-104">コンストラクター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="1d96f-104">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="1d96f-105">[クラス](../../language-reference/keywords/class.md)または[構造体](../../language-reference/builtin-types/struct.md)を作成するたびに、コンストラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-105">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="1d96f-106">クラスまたは構造体には、異なる引数を取るコンストラクターが複数含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="1d96f-106">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="1d96f-107">プログラマーはコンストラクターを利用することで、既定値を設定したり、インスタンス化を制限したり、柔軟で読みやすいコードを記述したりできます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-107">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="1d96f-108">詳細と例については、「[コンストラクターの使用](./using-constructors.md)」と「[インスタンス コンストラクター](./instance-constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d96f-108">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="1d96f-109">パラメーターなしのコンストラクター</span><span class="sxs-lookup"><span data-stu-id="1d96f-109">Parameterless constructors</span></span>
  
<span data-ttu-id="1d96f-110">クラスにコンストラクターを指定しない場合、C# では既定でコンストラクターが 1 つ作成されます。そのコンストラクターによりオブジェクトがインスタンス化され、「[C# の既定値](../../language-reference/builtin-types/default-values.md)」の記事にある既定値にメンバー変数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-110">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="1d96f-111">構造体にコンストラクターを指定しない場合、C# では、*暗黙的なパラメーターなしのコンストラクター*を利用し、各フィールドがその既定値に自動的に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-111">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="1d96f-112">詳細と例については、「[インスタンス コンストラクター](instance-constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d96f-112">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="1d96f-113">コンストラクターの構文</span><span class="sxs-lookup"><span data-stu-id="1d96f-113">Constructor syntax</span></span>

<span data-ttu-id="1d96f-114">コンストラクターは、名前がその型の名前と同じメソッドです。</span><span class="sxs-lookup"><span data-stu-id="1d96f-114">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="1d96f-115">メソッド シグネチャには、メソッド名とそのパラメーター リストだけが含まれます。戻り値の型は含まれません。</span><span class="sxs-lookup"><span data-stu-id="1d96f-115">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="1d96f-116">次の例は、`Person` という名前のクラスのコンストラクターを示しています。</span><span class="sxs-lookup"><span data-stu-id="1d96f-116">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="1d96f-117">コンストラクターを 1 つのステートメントとして実装できる場合、[式の本体の定義](../statements-expressions-operators/expression-bodied-members.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-117">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="1d96f-118">次の例では、コンストラクターに *name* という名前の文字列パラメーターが 1 つある `Location` クラスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="1d96f-118">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="1d96f-119">式の本体の定義により `locationName` フィールドに引数が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1d96f-119">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="1d96f-120">静的コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1d96f-120">Static constructors</span></span>

<span data-ttu-id="1d96f-121">前の例には、表示されるすべてのインスタンス コンストラクターがあり、それが新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d96f-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="1d96f-122">クラスまたは構造体には静的コンストラクターを与えることもできます。静的コンストラクターは型の静的メンバーを初期化します。</span><span class="sxs-lookup"><span data-stu-id="1d96f-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="1d96f-123">静的コンストラクターにはパラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="1d96f-123">Static constructors are parameterless.</span></span> <span data-ttu-id="1d96f-124">静的コンストラクターを指定して静的フィールドを初期化しない場合、C# コンパイラは、「[C# 型の既定値](../../language-reference/builtin-types/default-values.md)」の記事にある既定値に静的フィールドを初期化します。</span><span class="sxs-lookup"><span data-stu-id="1d96f-124">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="1d96f-125">次の例では、静的コンストラクターを使用して静的フィールドを初期化しています。</span><span class="sxs-lookup"><span data-stu-id="1d96f-125">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="1d96f-126">式の本体の定義で静的コンストラクターを定義することもできます。次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d96f-126">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="1d96f-127">詳細と例については、「[静的コンストラクター](./static-constructors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d96f-127">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d96f-128">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d96f-128">In This Section</span></span>  

 [<span data-ttu-id="1d96f-129">コンストラクターの使用</span><span class="sxs-lookup"><span data-stu-id="1d96f-129">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="1d96f-130">インスタンス コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1d96f-130">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="1d96f-131">プライベート コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1d96f-131">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="1d96f-132">静的コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1d96f-132">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="1d96f-133">コピー コンストラクターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="1d96f-133">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d96f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d96f-134">See also</span></span>

- [<span data-ttu-id="1d96f-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1d96f-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1d96f-136">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="1d96f-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="1d96f-137">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="1d96f-137">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="1d96f-138">static</span><span class="sxs-lookup"><span data-stu-id="1d96f-138">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="1d96f-139">初期化子がコンストラクターとは反対の順序で実行される理由その 1</span><span class="sxs-lookup"><span data-stu-id="1d96f-139">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
