---
title: 抽象クラスとシール クラス、およびクラス メンバー - C# プログラミング ガイド
description: C# の抽象キーワードによって、不完全なクラスとクラス メンバーが作成されます。 シール キーワードによって、以前の仮想クラスまたはクラス メンバーの継承が防止されます。
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: ccbc6734d4e9bafe059dd45bfdf82af7c84438a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204035"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="1b4eb-104">抽象クラスとシール クラス、およびクラス メンバー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="1b4eb-104">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>

<span data-ttu-id="1b4eb-105">[abstract](../../language-reference/keywords/abstract.md) キーワードを使用すると、派生クラスで実装する必要のある不完全な[クラス](../../language-reference/keywords/class.md) メンバーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-105">The [abstract](../../language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="1b4eb-106">また、[sealed](../../language-reference/keywords/sealed.md) キーワードを使用すると、既に [virtual](../../language-reference/keywords/virtual.md) とマークされているクラスや特定のクラス メンバーを継承しないようにできます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-106">The [sealed](../../language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="1b4eb-107">抽象クラスと抽象クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="1b4eb-107">Abstract Classes and Class Members</span></span>  

 <span data-ttu-id="1b4eb-108">クラス定義の前にキーワード `abstract` を指定することで、クラスを抽象として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-108">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="1b4eb-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 <span data-ttu-id="1b4eb-110">抽象クラスはインスタンス化できません。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-110">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="1b4eb-111">抽象クラスの目的は、複数の派生クラスで共有できる基底クラスの共通の定義を提供することです。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-111">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="1b4eb-112">たとえば、クラス ライブラリでは、その多くの関数のパラメーターとして使用される抽象クラスを定義できます。このライブラリを使用する場合は、派生クラスを作成してクラスの独自の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-112">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="1b4eb-113">抽象クラスでは、抽象メソッドも定義できます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-113">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="1b4eb-114">抽象メソッドを定義するには、メソッドの戻り値の型の前に `abstract` キーワードを記述します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-114">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="1b4eb-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 <span data-ttu-id="1b4eb-116">抽象メソッドには実装がないので、メソッド定義の後に、通常のメソッド ブロックの代わりにセミコロン (;) を配置します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="1b4eb-117">抽象クラスの派生クラスでは、すべての抽象メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="1b4eb-118">抽象クラスが基底クラスから仮想メソッドを継承した場合は、この抽象クラスでは抽象メソッドで仮想メソッドをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="1b4eb-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-119">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 <span data-ttu-id="1b4eb-120">`virtual` メソッドが `abstract` として宣言されている場合、そのメソッドは、その抽象クラスを継承するどのクラスでも仮想になります。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-120">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="1b4eb-121">抽象メソッドを継承するクラスでは、そのメソッドの元の実装にアクセスできません。上の例では、クラス F の `DoWork` は、クラス D の `DoWork` を呼び出すことができません。このようにして抽象クラスは、派生クラスに対し、仮想メソッドの新しいメソッド実装を強制的に提供させることができます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-121">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="1b4eb-122">シール クラスとシール クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="1b4eb-122">Sealed Classes and Class Members</span></span>  

 <span data-ttu-id="1b4eb-123">クラス定義の前にキーワード `sealed` を指定することで、クラスを [sealed](../../language-reference/keywords/sealed.md) として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-123">Classes can be declared as [sealed](../../language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="1b4eb-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-124">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 <span data-ttu-id="1b4eb-125">シール クラスは、基底クラスとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-125">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="1b4eb-126">このため、シール クラスは抽象クラスになることもできません。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-126">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="1b4eb-127">シール クラスにより、派生が防止されます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-127">Sealed classes prevent derivation.</span></span> <span data-ttu-id="1b4eb-128">シール クラスは基底クラスとして使用できないので、実行時の最適化で、シール クラス メンバーを多少高速に呼び出すことができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-128">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="1b4eb-129">基底クラスの仮想メンバーをオーバーライドしている派生クラスのメソッド、インデクサー、プロパティ、またはイベントでは、そのメンバーをシールとして宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-129">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="1b4eb-130">これにより、その後の派生クラスでは、メンバーの仮想性が無効になります。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-130">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="1b4eb-131">このように宣言するには、クラス メンバー宣言で [override](../../language-reference/keywords/override.md) キーワードの前に `sealed` キーワードを配置します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-131">This is accomplished by putting the `sealed` keyword before the [override](../../language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="1b4eb-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4eb-132">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="1b4eb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b4eb-133">See also</span></span>

- [<span data-ttu-id="1b4eb-134">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1b4eb-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1b4eb-135">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="1b4eb-135">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="1b4eb-136">継承</span><span class="sxs-lookup"><span data-stu-id="1b4eb-136">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="1b4eb-137">メソッド</span><span class="sxs-lookup"><span data-stu-id="1b4eb-137">Methods</span></span>](./methods.md)
- [<span data-ttu-id="1b4eb-138">フィールド</span><span class="sxs-lookup"><span data-stu-id="1b4eb-138">Fields</span></span>](./fields.md)
- [<span data-ttu-id="1b4eb-139">抽象プロパティを定義する方法</span><span class="sxs-lookup"><span data-stu-id="1b4eb-139">How to define abstract properties</span></span>](./how-to-define-abstract-properties.md)
