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
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741736"
---
# <a name="constructor-design"></a><span data-ttu-id="9f048-102">コンストラクターのデザイン</span><span class="sxs-lookup"><span data-stu-id="9f048-102">Constructor Design</span></span>

<span data-ttu-id="9f048-103">コンストラクターには、型コンストラクターとインスタンスコンストラクターの2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9f048-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="9f048-104">型コンストラクターは静的であり、型が使用される前に CLR によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f048-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="9f048-105">インスタンスコンストラクターは、型のインスタンスが作成されるときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f048-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="9f048-106">型コンストラクターはパラメーターを受け取ることができません。</span><span class="sxs-lookup"><span data-stu-id="9f048-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="9f048-107">インスタンスコンストラクターは使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f048-107">Instance constructors can.</span></span> <span data-ttu-id="9f048-108">パラメーターを受け取らないインスタンスコンストラクターは、通常、パラメーターなしのコンストラクターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9f048-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="9f048-109">コンストラクターは、型のインスタンスを作成する最も自然な方法です。</span><span class="sxs-lookup"><span data-stu-id="9f048-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="9f048-110">ほとんどの開発者は、インスタンスを作成する別の方法 (ファクトリメソッドなど) を検討する前に、コンストラクターを検索して使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="9f048-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="9f048-111">✔️単純で、理想的な既定のコンストラクターを提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9f048-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="9f048-112">単純なコンストラクターには、ごく少数のパラメーターがあり、すべてのパラメーターはプリミティブまたは列挙型です。</span><span class="sxs-lookup"><span data-stu-id="9f048-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="9f048-113">このような単純なコンストラクターにより、フレームワークの使いやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="9f048-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="9f048-114">目的の操作のセマンティクスが新しいインスタンスの構築に直接マップされない場合、またはコンストラクターのデザインガイドラインに従って不自然な場合は、コンストラクターの代わりに静的ファクトリメソッドを使用することを✔️します。</span><span class="sxs-lookup"><span data-stu-id="9f048-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="9f048-115">✔️メインプロパティを設定するためのショートカットとしてコンストラクターパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f048-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="9f048-116">空のコンストラクターを使用した後にいくつかのプロパティセットを使用し、複数の引数を持つコンストラクターを使用すると、セマンティクスに違いはありません。</span><span class="sxs-lookup"><span data-stu-id="9f048-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="9f048-117">コンストラクターパラメーターを使用してプロパティを設定するだけの場合は、コンストラクターパラメーターとプロパティに同じ名前を使用✔️ます。</span><span class="sxs-lookup"><span data-stu-id="9f048-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="9f048-118">このようなパラメーターとプロパティの違いは、大文字と小文字を区別することだけです。</span><span class="sxs-lookup"><span data-stu-id="9f048-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="9f048-119">コンストラクターで✔️最小限の作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f048-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="9f048-120">コンストラクターでは、コンストラクターパラメーターをキャプチャする以外に多くの作業を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9f048-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="9f048-121">その他の処理のコストは、必要になるまで延期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f048-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="9f048-122">✔️は、必要に応じてインスタンスコンストラクターから例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9f048-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="9f048-123">このようなコンストラクターが必要な場合は、クラスでパブリックのパラメーターなしのコンストラクターを明示的に宣言✔️ます。</span><span class="sxs-lookup"><span data-stu-id="9f048-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="9f048-124">型のコンストラクターを明示的に宣言しない場合、多くの言語 ( C#など) によって、パブリックなパラメーターなしのコンストラクターが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9f048-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="9f048-125">(抽象クラスは、保護されたコンストラクターを取得します)。</span><span class="sxs-lookup"><span data-stu-id="9f048-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="9f048-126">パラメーター化されたコンストラクターをクラスに追加すると、コンパイラはパラメーターなしのコンストラクターを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9f048-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="9f048-127">これにより、誤って重大な変更が行われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="9f048-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="9f048-128">❌ は、構造体でパラメーターなしのコンストラクターを明示的に定義しないようにします。</span><span class="sxs-lookup"><span data-stu-id="9f048-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="9f048-129">これにより、パラメーターなしのコンストラクターが定義されていない場合に、配列内のすべてのスロットで実行する必要がないため、配列の作成が高速になります。</span><span class="sxs-lookup"><span data-stu-id="9f048-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="9f048-130">多くのコンパイラ (を含むC#) では、このような理由で構造体にパラメーターなしのコンストラクターを使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f048-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="9f048-131">コンストラクター内のオブジェクトで仮想メンバーを呼び出さないように ❌ ます。</span><span class="sxs-lookup"><span data-stu-id="9f048-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="9f048-132">仮想メンバーを呼び出すと、最も派生した型のコンストラクターがまだ完全には実行されていない場合でも、最も派生されたオーバーライドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9f048-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="9f048-133">型コンストラクターのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9f048-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="9f048-134">静的コンストラクターをプライベートに設定✔️ます。</span><span class="sxs-lookup"><span data-stu-id="9f048-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="9f048-135">静的コンストラクター (クラスコンストラクターとも呼ばれます) を使用して、型を初期化します。</span><span class="sxs-lookup"><span data-stu-id="9f048-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="9f048-136">CLR は、型の最初のインスタンスが作成される前、またはその型の静的メンバーが呼び出される前に、静的コンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9f048-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="9f048-137">静的コンストラクターが呼び出されるタイミングは、ユーザーが制御できません。</span><span class="sxs-lookup"><span data-stu-id="9f048-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="9f048-138">静的コンストラクターがプライベートでない場合は、CLR 以外のコードで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9f048-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="9f048-139">コンストラクターで実行される操作によっては、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f048-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="9f048-140">コンパイラC#は、静的コンストラクターを強制的にプライベートにします。</span><span class="sxs-lookup"><span data-stu-id="9f048-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="9f048-141">❌ は、静的コンストラクターから例外をスローしません。</span><span class="sxs-lookup"><span data-stu-id="9f048-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="9f048-142">型コンストラクターから例外がスローされた場合、その型は現在のアプリケーションドメインでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9f048-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="9f048-143">静的コンストラクターを明示的に使用するのではなく、静的フィールドをインラインで初期化することを検討してください。これは、明示的に定義された静的コンストラクターを持たない型のパフォーマンスをランタイムが最適化できるためです。✔️</span><span class="sxs-lookup"><span data-stu-id="9f048-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="9f048-144">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="9f048-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="9f048-145">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="9f048-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9f048-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f048-146">See also</span></span>

- [<span data-ttu-id="9f048-147">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9f048-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="9f048-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9f048-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
