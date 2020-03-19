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
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401245"
---
# <a name="constructor-design"></a><span data-ttu-id="71769-102">コンストラクターのデザイン</span><span class="sxs-lookup"><span data-stu-id="71769-102">Constructor Design</span></span>

<span data-ttu-id="71769-103">コンストラクターには、型コンストラクターとインスタンス コンストラクターの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="71769-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="71769-104">型コンストラクターは静的であり、型が使用される前に CLR によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="71769-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="71769-105">インスタンス コンストラクターは、型のインスタンスが作成されるときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="71769-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="71769-106">型コンストラクタはパラメータを受け取ることができません。</span><span class="sxs-lookup"><span data-stu-id="71769-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="71769-107">インスタンス コンストラクターは、できます。</span><span class="sxs-lookup"><span data-stu-id="71769-107">Instance constructors can.</span></span> <span data-ttu-id="71769-108">パラメーターを受け取らないインスタンス コンストラクターは、パラメーターなしのコンストラクターと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="71769-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="71769-109">コンストラクタは、型のインスタンスを作成する最も自然な方法です。</span><span class="sxs-lookup"><span data-stu-id="71769-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="71769-110">ほとんどの開発者は、インスタンスを作成する別の方法 (ファクトリ メソッドなど) を検討する前に、コンストラクタを検索して使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="71769-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="71769-111">✔️は、単純で理想的なデフォルトのコンストラクタを提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="71769-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="71769-112">単純なコンストラクターは、パラメーターの数が非常に少なくて、すべてのパラメーターはプリミティブまたは列挙型です。</span><span class="sxs-lookup"><span data-stu-id="71769-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="71769-113">このような単純なコンストラクタは、フレームワークの使いやすさを高める。</span><span class="sxs-lookup"><span data-stu-id="71769-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="71769-114">✔️必要な操作のセマンティクスが新しいインスタンスの構築に直接マップされない場合、またはコンストラクタ設計ガイドラインに従う際に不自然な場合は、コンストラクタの代わりに静的ファクトリメソッドを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="71769-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="71769-115">メイン プロパティを設定するためのショートカットとしてコンストラクタ パラメータを使用✔️。</span><span class="sxs-lookup"><span data-stu-id="71769-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="71769-116">空のコンストラクタの後に何らかのプロパティセットを使用することと、複数の引数を持つコンストラクタを使用する場合のセマンティクスに違いはありません。</span><span class="sxs-lookup"><span data-stu-id="71769-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="71769-117">コンストラクターパラメーターを使用して単にプロパティを設定する場合は、コンストラクターパラメーターとプロパティに同じ名前を使用✔️ DO。</span><span class="sxs-lookup"><span data-stu-id="71769-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="71769-118">このようなパラメータとプロパティの違いは大文字と小文字の区別だけです。</span><span class="sxs-lookup"><span data-stu-id="71769-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="71769-119">✔️コンストラクタで最小限の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="71769-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="71769-120">コンストラクターは、コンストラクター パラメーターをキャプチャする以外に多くの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="71769-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="71769-121">他の処理のコストは、必要になるまで遅延する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71769-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="71769-122">必要に応じて、インスタンス コンストラクターから例外をスロー✔️ DO。</span><span class="sxs-lookup"><span data-stu-id="71769-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="71769-123">✔️は、クラスで public パラメーターなしのコンストラクターを明示的に宣言します (そのようなコンストラクターが必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="71769-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="71769-124">型のコンストラクターを明示的に宣言しない場合、多くの言語 (C# など) は、パラメーターなしのパブリック コンストラクターを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="71769-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="71769-125">(抽象クラスは、プロテクト コンストラクタを取得します。</span><span class="sxs-lookup"><span data-stu-id="71769-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="71769-126">パラメーター化されたコンストラクターをクラスに追加すると、コンパイラはパラメーターなしのコンストラクターを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="71769-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="71769-127">これにより、誤って破損した変更が発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="71769-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="71769-128">❌構造体にパラメーターなしのコンストラクターを明示的に定義する回避。</span><span class="sxs-lookup"><span data-stu-id="71769-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="71769-129">これにより、パラメーターなしのコンストラクターが定義されていない場合、配列内のすべてのスロットで実行する必要がないため、配列の作成が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="71769-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="71769-130">C# を含む多くのコンパイラでは、このような理由で構造体にパラメーターなしのコンストラクターを含めることができない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="71769-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="71769-131">❌コンストラクタ内のオブジェクトの仮想メンバーを呼び出すことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="71769-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="71769-132">仮想メンバーを呼び出すと、最派生型のコンストラクターがまだ完全に実行されていない場合でも、最も派生したオーバーライドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71769-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="71769-133">型コンストラクタのガイドライン</span><span class="sxs-lookup"><span data-stu-id="71769-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="71769-134">静的コンストラクターをプライベートに✔️します。</span><span class="sxs-lookup"><span data-stu-id="71769-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="71769-135">静的コンストラクターは、クラス コンストラクターとも呼ばれ、型の初期化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="71769-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="71769-136">CLR は、型の最初のインスタンスが作成される前に静的コンストラクターを呼び出すか、その型の静的メンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71769-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="71769-137">ユーザーは、静的コンストラクターが呼び出されたときに制御できません。</span><span class="sxs-lookup"><span data-stu-id="71769-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="71769-138">静的コンストラクターがプライベートでない場合は、CLR 以外のコードから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="71769-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="71769-139">コンストラクターで実行される操作によっては、予期しない動作が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="71769-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="71769-140">C# コンパイラは、静的コンストラクターをプライベートに強制します。</span><span class="sxs-lookup"><span data-stu-id="71769-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="71769-141">❌静的コンストラクターから例外をスローしないでください。</span><span class="sxs-lookup"><span data-stu-id="71769-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="71769-142">型コンストラクターから例外がスローされた場合、その型は現在のアプリケーション ドメインで使用できません。</span><span class="sxs-lookup"><span data-stu-id="71769-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="71769-143">✔️は、静的コンストラクターを明示的に使用するのではなく、静的フィールドをインラインで初期化します。</span><span class="sxs-lookup"><span data-stu-id="71769-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="71769-144">*2005年、2009年©マイクロソフト株式会社。すべての権利が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="71769-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="71769-145">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="71769-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="71769-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="71769-146">See also</span></span>

- [<span data-ttu-id="71769-147">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="71769-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="71769-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="71769-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
