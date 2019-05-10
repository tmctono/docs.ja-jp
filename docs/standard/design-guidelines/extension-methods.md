---
title: 拡張メソッド
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: 1835f84a5126ef07adbe119089d2d943ffda18cd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615287"
---
# <a name="extension-methods"></a><span data-ttu-id="a72b4-102">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="a72b4-102">Extension Methods</span></span>
<span data-ttu-id="a72b4-103">拡張メソッドは、言語機能により、インスタンス メソッドの呼び出し構文を使用して呼び出される静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a72b4-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="a72b4-104">これらのメソッドは、メソッドは、操作の対象のインスタンスを表す 1 つ以上のパラメーターを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>  
  
 <span data-ttu-id="a72b4-105">このような拡張メソッドを定義するクラスは、「スポンサー」クラスと呼ばれます、静的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="a72b4-106">拡張メソッドを使用するには、スポンサー クラスを定義する名前空間をインポート 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>  
  
 <span data-ttu-id="a72b4-107">**X AVOID** いないこと、お持ちでない型に特に拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-107">**X AVOID** frivolously defining extension methods, especially on types you don’t own.</span></span>  
  
 <span data-ttu-id="a72b4-108">型のソース コードを所有している場合は、通常のインスタンス メソッドを代わりに使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a72b4-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="a72b4-109">所有していない場合に、メソッドを追加するには、十分に注意します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="a72b4-110">自由に使用して拡張メソッドでは、これらのメソッドを使用してデザインされていない型の Api に混乱が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>  
  
 <span data-ttu-id="a72b4-111">**✓ CONSIDER** 拡張メソッドを使用して、次のシナリオのいずれかで。</span><span class="sxs-lookup"><span data-stu-id="a72b4-111">**✓ CONSIDER** using extension methods in any of the following scenarios:</span></span>  
  
- <span data-ttu-id="a72b4-112">ヘルパーを提供するには、コア インターフェイスの観点からは機能している場合、インターフェイスのすべての実装に関連する機能を記述できます。</span><span class="sxs-lookup"><span data-stu-id="a72b4-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="a72b4-113">具体的な実装は、インターフェイスにそれ以外の場合割り当てることはできないためにです。</span><span class="sxs-lookup"><span data-stu-id="a72b4-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="a72b4-114">たとえば、`LINQ to Objects`演算子は、すべての拡張メソッドとして実装されます<xref:System.Collections.Generic.IEnumerable%601>型。</span><span class="sxs-lookup"><span data-stu-id="a72b4-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="a72b4-115">そのため、いずれか`IEnumerable<>`実装は、LINQ で自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="a72b4-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>  
  
- <span data-ttu-id="a72b4-116">インスタンス メソッドがいくつかの型への依存関係がこのような依存関係をどのように導入するときに、依存関係の管理規則ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="a72b4-117">依存関係など<xref:System.String>に<xref:System.Uri?displayProperty=nameWithType>はおそらく、望ましくないため、`String.ToUri()`インスタンス メソッドが返す`System.Uri`依存関係の管理の観点から正しくない設計になります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="a72b4-118">静的な拡張メソッド`Uri.ToUri(this string str)`返す`System.Uri`はるかに優れた設計になります。</span><span class="sxs-lookup"><span data-stu-id="a72b4-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>  
  
 <span data-ttu-id="a72b4-119">**X AVOID** で拡張メソッドを定義する<xref:System.Object?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="a72b4-119">**X AVOID** defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a72b4-120">VB のユーザーは拡張メソッド構文を使用してオブジェクト参照でこのようなメソッドを呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="a72b4-120">VB users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="a72b4-121">VB は VB での参照を宣言するオブジェクトが遅延するすべてのメソッド呼び出しを強制的にバインドされているため、このようなメソッドの呼び出しをサポートしていません (と呼ばれる実際のメンバーは実行時に決定されます)、拡張メソッドへのバインドは、コンパイル時 (事前に決定中バインドされている場合)。</span><span class="sxs-lookup"><span data-stu-id="a72b4-121">VB does not support calling such methods because, in VB, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>  
  
 <span data-ttu-id="a72b4-122">同じバインディング動作が存在する場合は、他の言語にガイドラインが適用されることに注意してください。 または、拡張メソッドがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a72b4-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>  
  
 <span data-ttu-id="a72b4-123">**X DO NOT** インターフェイスにメソッドを追加または依存関係の管理用である場合を除き、拡張の型と同じ名前空間の拡張メソッドを格納します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-123">**X DO NOT** put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>  
  
 <span data-ttu-id="a72b4-124">**X AVOID** 異なる名前空間にある場合でも、同じシグネチャを持つ 2 つ以上の拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-124">**X AVOID** defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>  
  
 <span data-ttu-id="a72b4-125">**✓ CONSIDER** 型がインターフェイスで、ほとんどまたはすべてのケースで使用する拡張メソッドは、拡張された型と同じ名前空間に拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-125">**✓ CONSIDER** defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>  
  
 <span data-ttu-id="a72b4-126">**X DO NOT** 通常その他の機能に関連付けられている名前空間の機能を実装する拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-126">**X DO NOT** define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="a72b4-127">代わりに、所属する機能に関連付けられている名前空間で定義します。</span><span class="sxs-lookup"><span data-stu-id="a72b4-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>  
  
 <span data-ttu-id="a72b4-128">**X AVOID** 拡張メソッド (たとえば、「拡張」) を専用の名前空間の汎用名前付けします。</span><span class="sxs-lookup"><span data-stu-id="a72b4-128">**X AVOID** generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="a72b4-129">わかりやすい名前を (たとえば、「ルーティング」) 代わりにします。</span><span class="sxs-lookup"><span data-stu-id="a72b4-129">Use a descriptive name (e.g., "Routing") instead.</span></span>  
  
 <span data-ttu-id="a72b4-130">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="a72b4-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a72b4-131">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="a72b4-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72b4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a72b4-132">See also</span></span>

- [<span data-ttu-id="a72b4-133">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a72b4-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="a72b4-134">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a72b4-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
