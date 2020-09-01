---
description: abstract - C# リファレンス
title: abstract - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 095c4dea838aff4f14833d78fb10a2f831cf5173
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127205"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="da95d-103">abstract (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="da95d-103">abstract (C# Reference)</span></span>
<span data-ttu-id="da95d-104">`abstract` 修飾子は、その修飾対象の実装が不足しているか、不完全であることを示します。</span><span class="sxs-lookup"><span data-stu-id="da95d-104">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="da95d-105">クラスやメソッド、プロパティ、インデクサー、イベントと組み合わせて abstract 修飾子を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="da95d-105">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="da95d-106">クラス宣言に `abstract` 修飾子を使用して、クラスは他のクラスの基底クラスとしてのみ使用することを意図し、それ自体ではインスタンス化されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="da95d-106">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="da95d-107">abstract としてマークされたメンバーは、その抽象クラスから派生した非抽象クラスによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-107">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="da95d-108">例</span><span class="sxs-lookup"><span data-stu-id="da95d-108">Example</span></span>  
 <span data-ttu-id="da95d-109">この例で、`GetArea` の機能は、`Shape` から派生している `Square` クラスで実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-109">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="da95d-110">抽象クラスには次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-110">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="da95d-111">抽象クラスはインスタンス化できません。</span><span class="sxs-lookup"><span data-stu-id="da95d-111">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="da95d-112">抽象クラスには抽象メソッドとアクセサーを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="da95d-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="da95d-113">[sealed](./sealed.md) 修飾子を使って抽象クラスを修飾することはできません。2 つの修飾子が逆の意味を持つためです。</span><span class="sxs-lookup"><span data-stu-id="da95d-113">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="da95d-114">`sealed` 修飾子を指定したクラスは継承が禁止されるのに対し、`abstract` 修飾子を指定したクラスは継承による使用が強制されます。</span><span class="sxs-lookup"><span data-stu-id="da95d-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="da95d-115">抽象クラスから派生した具象クラスには、継承されたすべての抽象メソッドとアクセサーの実際の機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="da95d-116">メソッドまたはプロパティに機能が実装されていないことを示すには、そのメソッドまたはプロパティの宣言で `abstract` 修飾子を使います。</span><span class="sxs-lookup"><span data-stu-id="da95d-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="da95d-117">抽象メソッドには次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-117">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="da95d-118">抽象メソッドは、仮想メソッドの性質を暗に含んでいます。</span><span class="sxs-lookup"><span data-stu-id="da95d-118">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="da95d-119">抽象メソッドの宣言は、抽象クラスでしか認められません。</span><span class="sxs-lookup"><span data-stu-id="da95d-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="da95d-120">抽象メソッドの宣言には実際の機能が実装されないため、メソッドの本体はありません。つまり、メソッドの宣言は、末尾のセミコロンがあるだけで、シグネチャの後ろに中かっこ ({ }) は存在しません。</span><span class="sxs-lookup"><span data-stu-id="da95d-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="da95d-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da95d-121">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="da95d-122">実際の機能は、メソッド (具象クラスのメンバー) に [override](./override.md) を指定して実装します。</span><span class="sxs-lookup"><span data-stu-id="da95d-122">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="da95d-123">抽象メソッドの宣言に [static](./static.md) 修飾子や [virtual](./virtual.md) 修飾子を使うのは誤りです。</span><span class="sxs-lookup"><span data-stu-id="da95d-123">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="da95d-124">抽象プロパティは、宣言と呼び出しの構文の違いを除けば、抽象メソッドと似た働きを持ちます。</span><span class="sxs-lookup"><span data-stu-id="da95d-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="da95d-125">`abstract` 修飾子を静的プロパティに対して使うのは誤りです。</span><span class="sxs-lookup"><span data-stu-id="da95d-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="da95d-126">継承する抽象プロパティは、派生クラス内で [override](./override.md) 修飾子を使ったプロパティ宣言を記述することでオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="da95d-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="da95d-127">抽象クラスの詳細については、「[抽象クラスとシール クラス、およびクラス メンバー](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da95d-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="da95d-128">すべてのインターフェイス メンバーの機能は、抽象クラスで実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da95d-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="da95d-129">インターフェイスを実装する抽象クラスで、インターフェイス メソッドを抽象メソッドにマップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="da95d-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="da95d-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da95d-130">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="da95d-131">例</span><span class="sxs-lookup"><span data-stu-id="da95d-131">Example</span></span>  
 <span data-ttu-id="da95d-132">この例の `DerivedClass` クラスは、抽象クラス `BaseClass` から派生しています。</span><span class="sxs-lookup"><span data-stu-id="da95d-132">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="da95d-133">この抽象クラスには、`AbstractMethod` という抽象メソッドのほか、`X` と `Y` の 2 つの抽象プロパティが存在します。</span><span class="sxs-lookup"><span data-stu-id="da95d-133">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="da95d-134">この例の抽象クラスを次のようなステートメントでインスタンス化しようとするとどうなるかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da95d-134">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="da95d-135">このように、抽象クラス 'BaseClass' のインスタンスをコンパイラが作成できないことを伝えるエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="da95d-135">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="da95d-136">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="da95d-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da95d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="da95d-137">See also</span></span>

- [<span data-ttu-id="da95d-138">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="da95d-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="da95d-139">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="da95d-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="da95d-140">修飾子</span><span class="sxs-lookup"><span data-stu-id="da95d-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="da95d-141">virtual</span><span class="sxs-lookup"><span data-stu-id="da95d-141">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="da95d-142">override</span><span class="sxs-lookup"><span data-stu-id="da95d-142">override</span></span>](./override.md)
- [<span data-ttu-id="da95d-143">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="da95d-143">C# Keywords</span></span>](./index.md)
