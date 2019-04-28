---
title: コンストラクターのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: 68192e3b75a120c73b82c34005d4dee650540bf3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925464"
---
# <a name="constructor-design"></a><span data-ttu-id="06c17-102">コンストラクターのデザイン</span><span class="sxs-lookup"><span data-stu-id="06c17-102">Constructor Design</span></span>
<span data-ttu-id="06c17-103">コンス トラクターの 2 種類があります: コンス トラクターとインスタンス コンス トラクターを入力します。</span><span class="sxs-lookup"><span data-stu-id="06c17-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="06c17-104">型コンス トラクターは、静的型を使用する前に、CLR で実行されます。</span><span class="sxs-lookup"><span data-stu-id="06c17-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="06c17-105">インスタンス コンス トラクターは、型のインスタンスが作成されるときに実行します。</span><span class="sxs-lookup"><span data-stu-id="06c17-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="06c17-106">型のコンス トラクターは、すべてのパラメーターを受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="06c17-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="06c17-107">インスタンス コンス トラクターができます。</span><span class="sxs-lookup"><span data-stu-id="06c17-107">Instance constructors can.</span></span> <span data-ttu-id="06c17-108">すべてのパラメーターを使用しないインスタンスのコンス トラクターは、既定のコンス トラクターとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="06c17-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="06c17-109">コンス トラクターは、型のインスタンスを作成する最も自然な方法です。</span><span class="sxs-lookup"><span data-stu-id="06c17-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="06c17-110">ほとんどの開発者は検索し、別のファクトリ メソッド) などのインスタンスを作成する方法を検討する前に、コンス トラクターを使用しようとしています。</span><span class="sxs-lookup"><span data-stu-id="06c17-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="06c17-111">**✓ CONSIDER** simple、理想的には、既定コンス トラクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="06c17-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="06c17-112">簡単なコンス トラクターがパラメーター数が非常に小さいと、すべてのパラメーターがプリミティブまたは列挙型。</span><span class="sxs-lookup"><span data-stu-id="06c17-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="06c17-113">このような単純なコンス トラクターは、フレームワークのユーザビリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="06c17-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="06c17-114">**✓ CONSIDER** 目的の操作のセマンティクスは、新しいインスタンスの構築に直接マップされない場合、またはコンス トラクターのデザイン ガイドラインに従うが不自然にコンス トラクターではなく静的ファクトリ メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c17-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="06c17-115">**✓ DO** 主要なプロパティを設定するためのショートカットとしてコンス トラクターのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c17-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="06c17-116">意味的に同じことはありませんで一部のプロパティ セットの後に空のコンス トラクターと複数の引数をコンス トラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c17-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="06c17-117">**✓ DO** コンス トラクターのパラメーターを使用して単にプロパティを設定する場合は、コンス トラクターのパラメーターとプロパティに同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="06c17-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="06c17-118">このようなパラメーターとプロパティの唯一の違い大文字小文字の区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c17-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="06c17-119">**✓ DO** コンス トラクターで作業を最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="06c17-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="06c17-120">コンス トラクターは、キャプチャ以外処理がコンス トラクターのパラメーターを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="06c17-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="06c17-121">他の処理のコストは、必要になるまで遅延する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c17-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="06c17-122">**✓ DO** 該当する場合は、インスタンス コンス トラクターから例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06c17-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="06c17-123">**✓ DO** コンス トラクターが必要な場合に、クラスでは、パブリックの既定のコンス トラクターを明示的に宣言します。</span><span class="sxs-lookup"><span data-stu-id="06c17-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="06c17-124">型のコンス トラクターを明示的に宣言しない、多くの言語 (c#) などにパブリックの既定のコンス トラクターが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="06c17-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="06c17-125">(抽象クラスは、保護されたコンス トラクターを取得します)。</span><span class="sxs-lookup"><span data-stu-id="06c17-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="06c17-126">クラスにパラメーター化されたコンス トラクターを追加すると、コンパイラは既定のコンス トラクターを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="06c17-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="06c17-127">これにより、多くの場合、偶発的な重大な変更が原因です。</span><span class="sxs-lookup"><span data-stu-id="06c17-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="06c17-128">**X AVOID** 構造体の既定のコンス トラクターを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="06c17-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="06c17-129">これにより、配列の作成より速く、既定のコンス トラクターが定義されていない場合、配列内のすべてのスロット上で実行することはないためです。</span><span class="sxs-lookup"><span data-stu-id="06c17-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="06c17-130">など、C# の場合、多くのコンパイラがこの理由をパラメーターなしのコンス トラクターを持つ構造体を許可しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="06c17-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="06c17-131">**X AVOID** コンス トラクター内のオブジェクトでの仮想メンバーを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="06c17-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="06c17-132">仮想メンバーを呼び出すことにより、大多数の派生型のコンス トラクターが実行されていない完全にまだ場合でも、呼び出される最派生のオーバーライドが発生します。</span><span class="sxs-lookup"><span data-stu-id="06c17-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="06c17-133">型のコンス トラクターのガイドライン</span><span class="sxs-lookup"><span data-stu-id="06c17-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="06c17-134">**✓ DO** 静的コンス トラクターをプライベートに設定します。</span><span class="sxs-lookup"><span data-stu-id="06c17-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="06c17-135">クラスのコンス トラクターとも呼ばれる、静的コンス トラクターは、型の初期化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="06c17-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="06c17-136">型の最初のインスタンスが作成されるか、その型の静的メンバーを呼び出す前に、CLR は、静的コンス トラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="06c17-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="06c17-137">ユーザーには、静的コンス トラクターが呼び出されたときに制御がありません。</span><span class="sxs-lookup"><span data-stu-id="06c17-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="06c17-138">場合は、静的コンス トラクターがプライベートでは、CLR 以外のコードから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="06c17-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="06c17-139">コンス トラクターで実行される操作、によって予期しない動作ができます。</span><span class="sxs-lookup"><span data-stu-id="06c17-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="06c17-140">C# コンパイラでは、プライベート静的コンス トラクターを強制します。</span><span class="sxs-lookup"><span data-stu-id="06c17-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="06c17-141">**X DO NOT** 静的コンス トラクターから例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06c17-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="06c17-142">型コンス トラクターから例外がスローされた場合、型が現在のアプリケーション ドメインで使用できません。</span><span class="sxs-lookup"><span data-stu-id="06c17-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="06c17-143">**✓ CONSIDER** ランタイムが、明示的に定義された静的コンス トラクターを持たない型のパフォーマンスを最適化するために、静的コンス トラクターを明示的に使用するのではなく、静的フィールドをインラインを初期化します。</span><span class="sxs-lookup"><span data-stu-id="06c17-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="06c17-144">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="06c17-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="06c17-145">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="06c17-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c17-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="06c17-146">See also</span></span>

- [<span data-ttu-id="06c17-147">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="06c17-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="06c17-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="06c17-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
