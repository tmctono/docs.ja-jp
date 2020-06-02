---
title: 拡張メソッド
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 77c012d7838ae2fa1f62163bc58520db67c64ce5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289760"
---
# <a name="extension-methods"></a><span data-ttu-id="fb0cb-102">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="fb0cb-102">Extension methods</span></span>

<span data-ttu-id="fb0cb-103">拡張メソッドは、インスタンスメソッドの呼び出し構文を使用して静的メソッドを呼び出せるようにする言語機能です。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-103">Extension methods are a language feature that allows static methods to be called using instance-method call syntax.</span></span> <span data-ttu-id="fb0cb-104">これらのメソッドは、メソッドが操作するインスタンスを表す1つ以上のパラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>

 <span data-ttu-id="fb0cb-105">拡張メソッドを定義するクラスは "スポンサー" クラスと呼ばれ、として宣言する必要があり `static` ます。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-105">The class that defines an extension method is referred to as the "sponsor" class, and it must be declared as `static`.</span></span> <span data-ttu-id="fb0cb-106">拡張メソッドを使用するには、スポンサークラスを定義する名前空間をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-106">To use extension methods, you must import the namespace that defines the sponsor class.</span></span>

 <span data-ttu-id="fb0cb-107">❌特に所有していない型については、拡張メソッドの使用を避けてください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-107">❌ AVOID overuse of extension methods, especially on types you don't own.</span></span>

 <span data-ttu-id="fb0cb-108">型のソースコードを所有している場合は、代わりに通常のインスタンスメソッドを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="fb0cb-109">ソースコードを所有しておらず、メソッドを追加する場合は、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-109">If you don't own the source code and you want to add a method, be very careful.</span></span> <span data-ttu-id="fb0cb-110">拡張メソッドを自由に使用すると、これらのメソッドを使用するように設計されていない型の Api が乱雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>

 <span data-ttu-id="fb0cb-111">次のシナリオでは、拡張メソッドの使用を検討✔️。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-111">✔️ CONSIDER using extension methods in any of the following scenarios:</span></span>

- <span data-ttu-id="fb0cb-112">インターフェイスのすべての実装に関連するヘルパー機能を提供するために、がコアインターフェイスの観点で記述されている場合は、この機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="fb0cb-113">これは、具象実装がインターフェイスに割り当てられないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="fb0cb-114">たとえば、LINQ to Objects の演算子は、すべての型の拡張メソッドとして実装され <xref:System.Collections.Generic.IEnumerable%601> ます。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-114">For example, the LINQ to Objects operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="fb0cb-115">したがって、すべての `IEnumerable<>` 実装は自動的に LINQ 対応になります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>

- <span data-ttu-id="fb0cb-116">インスタンスメソッドで何らかの種類の依存関係が発生しても、そのような依存関係は依存関係管理規則に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="fb0cb-117">たとえば、からへの依存関係は <xref:System.String> <xref:System.Uri?displayProperty=nameWithType> 望ましくないと考えられます。そのため、を `String.ToUri()` 返すインスタンスメソッドは、 `System.Uri` 依存関係管理の観点からの不適切な設計になります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="fb0cb-118">を返す静的な拡張メソッドは、より `Uri.ToUri(this string str)` `System.Uri` 優れた設計になります。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>

 <span data-ttu-id="fb0cb-119">❌で拡張メソッドを定義することは避けて <xref:System.Object?displayProperty=nameWithType> ください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-119">❌ AVOID defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="fb0cb-120">Visual Basic ユーザーは、拡張メソッドの構文を使用して、オブジェクト参照に対してこのようなメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-120">Visual Basic users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="fb0cb-121">Visual Basic では、として参照を宣言すると、 `Object` すべてのメソッドの呼び出しが強制的に遅延バインディングされます (つまり、呼び出された実際のメンバーは実行時に決定されます)。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-121">In Visual Basic, declaring a reference as `Object` forces all method invocations on it to be late bound (which means the actual member called is determined at run time).</span></span> <span data-ttu-id="fb0cb-122">拡張メソッドへのバインディングは、コンパイル時 (事前バインディング) に決定されます。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-122">Bindings to extension methods are determined at compile time (early bound).</span></span>

 <span data-ttu-id="fb0cb-123">このガイドラインは、同じバインディング動作が存在するか、または拡張メソッドがサポートされていない他の言語に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-123">This guideline applies to other languages where the same binding behavior is present or where extension methods are not supported.</span></span>

 <span data-ttu-id="fb0cb-124">❌メソッドをインターフェイスに追加する場合や依存関係の管理用に使用する場合を除き、拡張メソッドを拡張型と同じ名前空間に配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-124">❌ DO NOT put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>

 <span data-ttu-id="fb0cb-125">❌異なる名前空間に存在する場合でも、同じシグネチャを持つ2つ以上の拡張メソッドを定義することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-125">❌ AVOID defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>

 <span data-ttu-id="fb0cb-126">型がインターフェイスであり、ほとんどの場合またはほとんどの場合に拡張メソッドを使用することを意図している場合は、拡張型と同じ名前空間で拡張メソッドを定義することを✔️してください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-126">✔️ CONSIDER defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>

 <span data-ttu-id="fb0cb-127">❌通常は他の機能に関連付けられている名前空間で、機能を実装する拡張メソッドを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-127">❌ DO NOT define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="fb0cb-128">代わりに、所属する機能に関連付けられている名前空間で定義します。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-128">Instead, define them in the namespace associated with the feature they belong to.</span></span>

 <span data-ttu-id="fb0cb-129">❌拡張メソッド専用の名前空間の汎用的な名前付け ("拡張機能" など) は避けてください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-129">❌ AVOID generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="fb0cb-130">代わりに、わかりやすい名前 ("Routing" など) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fb0cb-130">Use a descriptive name (e.g., "Routing") instead.</span></span>

 <span data-ttu-id="fb0cb-131">*部分 &copy; 2005、2009 Microsoft Corporation。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="fb0cb-131">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="fb0cb-132">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="fb0cb-132">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fb0cb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb0cb-133">See also</span></span>

- [<span data-ttu-id="fb0cb-134">メンバーデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="fb0cb-134">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="fb0cb-135">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="fb0cb-135">Framework Design Guidelines</span></span>](index.md)
