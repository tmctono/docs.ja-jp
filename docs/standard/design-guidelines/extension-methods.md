---
title: Extension のメソッド
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 13f92470b23d138e0d30bed947ff1932f2605d28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741621"
---
# <a name="extension-methods"></a><span data-ttu-id="1c504-102">Extension のメソッド</span><span class="sxs-lookup"><span data-stu-id="1c504-102">Extension Methods</span></span>
<span data-ttu-id="1c504-103">拡張メソッドは、インスタンスメソッド呼び出し構文を使用して静的メソッドを呼び出せるようにする言語機能です。</span><span class="sxs-lookup"><span data-stu-id="1c504-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="1c504-104">これらのメソッドは、メソッドが操作するインスタンスを表す1つ以上のパラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c504-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>

 <span data-ttu-id="1c504-105">このような拡張メソッドを定義するクラスは "スポンサー" クラスと呼ばれ、static として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c504-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="1c504-106">拡張メソッドを使用するには、スポンサークラスを定義する名前空間をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c504-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>

 <span data-ttu-id="1c504-107">frivolously は、特に所有していない型に対して拡張メソッドを定義しないように ❌ します。</span><span class="sxs-lookup"><span data-stu-id="1c504-107">❌ AVOID frivolously defining extension methods, especially on types you don’t own.</span></span>

 <span data-ttu-id="1c504-108">型のソースコードを所有している場合は、代わりに通常のインスタンスメソッドを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1c504-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="1c504-109">を所有しておらず、メソッドを追加する場合は、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="1c504-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="1c504-110">拡張メソッドを自由に使用すると、これらのメソッドを使用するように設計されていない型の Api が乱雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c504-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>

 <span data-ttu-id="1c504-111">次のシナリオでは、拡張メソッドの使用を検討✔️。</span><span class="sxs-lookup"><span data-stu-id="1c504-111">✔️ CONSIDER using extension methods in any of the following scenarios:</span></span>

- <span data-ttu-id="1c504-112">インターフェイスのすべての実装に関連するヘルパー機能を提供するために、がコアインターフェイスの観点で記述されている場合は、この機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c504-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="1c504-113">これは、具象実装がインターフェイスに割り当てられないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="1c504-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="1c504-114">たとえば、`LINQ to Objects` の演算子は、すべての <xref:System.Collections.Generic.IEnumerable%601> 型の拡張メソッドとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="1c504-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="1c504-115">したがって、`IEnumerable<>` の実装はすべて自動的に LINQ 対応になります。</span><span class="sxs-lookup"><span data-stu-id="1c504-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>

- <span data-ttu-id="1c504-116">インスタンスメソッドで何らかの種類の依存関係が発生しても、そのような依存関係は依存関係管理規則に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c504-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="1c504-117">たとえば、<xref:System.String> から <xref:System.Uri?displayProperty=nameWithType> への依存関係はおそらく望ましくありません。 `String.ToUri()` そのため `System.Uri` を返すインスタンスメソッドは、依存関係管理の観点からは不適切な設計になります。</span><span class="sxs-lookup"><span data-stu-id="1c504-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="1c504-118">`System.Uri` を返す静的な拡張メソッドは、より優れたデザインであることが `Uri.ToUri(this string str)` ます。</span><span class="sxs-lookup"><span data-stu-id="1c504-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>

 <span data-ttu-id="1c504-119">❌ <xref:System.Object?displayProperty=nameWithType>で拡張メソッドを定義することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="1c504-119">❌ AVOID defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="1c504-120">Visual Basic ユーザーは、拡張メソッドの構文を使用して、オブジェクト参照に対してこのようなメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1c504-120">Visual Basic users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="1c504-121">Visual Basic は、このようなメソッドの呼び出しをサポートしていません。これは、Visual Basic では、参照をオブジェクトとして宣言すると、すべてのメソッドの呼び出しが遅延バインディングされる (実際のメンバーは実行時に決定される) のに対し、拡張メソッドへのバインディングはで決定されるためです。コンパイル時 (事前バインディング)。</span><span class="sxs-lookup"><span data-stu-id="1c504-121">Visual Basic does not support calling such methods because, in Visual Basic, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>

 <span data-ttu-id="1c504-122">ガイドラインは、同じバインディング動作が存在する他の言語、または拡張メソッドがサポートされていない他の言語に適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c504-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>

 <span data-ttu-id="1c504-123">❌ メソッドをインターフェイスに追加する場合や依存関係の管理用に使用する場合を除き、拡張メソッドを拡張型と同じ名前空間に配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c504-123">❌ DO NOT put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>

 <span data-ttu-id="1c504-124">異なる名前空間に存在する場合でも、同じシグネチャを持つ2つ以上の拡張メソッドを定義する ❌ は避けてください。</span><span class="sxs-lookup"><span data-stu-id="1c504-124">❌ AVOID defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>

 <span data-ttu-id="1c504-125">型がインターフェイスであり、ほとんどの場合またはほとんどの場合に拡張メソッドを使用することを意図している場合は、拡張型と同じ名前空間で拡張メソッドを定義することを✔️してください。</span><span class="sxs-lookup"><span data-stu-id="1c504-125">✔️ CONSIDER defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>

 <span data-ttu-id="1c504-126">❌ は、通常は他の機能に関連付けられている名前空間の機能を実装する拡張メソッドを定義しません。</span><span class="sxs-lookup"><span data-stu-id="1c504-126">❌ DO NOT define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="1c504-127">代わりに、所属する機能に関連付けられている名前空間で定義します。</span><span class="sxs-lookup"><span data-stu-id="1c504-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>

 <span data-ttu-id="1c504-128">拡張メソッド専用の名前空間の汎用的な名前付けを回避 ❌ ("拡張機能" など)。</span><span class="sxs-lookup"><span data-stu-id="1c504-128">❌ AVOID generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="1c504-129">代わりに、わかりやすい名前 ("Routing" など) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1c504-129">Use a descriptive name (e.g., "Routing") instead.</span></span>

 <span data-ttu-id="1c504-130">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="1c504-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1c504-131">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="1c504-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1c504-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c504-132">See also</span></span>

- [<span data-ttu-id="1c504-133">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1c504-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="1c504-134">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1c504-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
