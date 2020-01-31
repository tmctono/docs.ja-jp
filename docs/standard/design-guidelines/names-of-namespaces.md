---
title: 名前空間の名前
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 52fee0dfaff284c2c1a6afcb8aa7530c28a60d65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744141"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="2ae99-102">名前空間の名前</span><span class="sxs-lookup"><span data-stu-id="2ae99-102">Names of Namespaces</span></span>
<span data-ttu-id="2ae99-103">他の命名ガイドラインと同様に、名前空間に名前を付ける際の目的は、名前空間の内容がどのようなものである可能性があるかをすぐに把握するために、フレームワークを使用するプログラマにとって十分なわかりやすいものにすることです。</span><span class="sxs-lookup"><span data-stu-id="2ae99-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="2ae99-104">次のテンプレートは、名前空間の名前付けに関する一般的な規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-104">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="2ae99-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-105">The following are examples:</span></span>

 <span data-ttu-id="2ae99-106">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="2ae99-106">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="2ae99-107">異なる企業の名前空間が同じ名前にならないように、会社名を使用して名前空間名にプレフィックスを付ける✔️ます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-107">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="2ae99-108">名前空間名の2番目のレベルでは、バージョンに依存しない安定した製品名を使用✔️ます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-108">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="2ae99-109">企業内のグループ名は有効期間が短くなる傾向があるため、名前空間階層内の名前の基準として組織階層を使用することは ❌ ません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-109">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="2ae99-110">関連するテクノロジのグループを中心に、名前空間の階層を整理します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-110">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="2ae99-111">✔️は、文字の大文字と小文字の区別を使用し、ピリオドを使用して名前空間コンポーネント (例: `Microsoft.Office.PowerPoint`) を区切ります。</span><span class="sxs-lookup"><span data-stu-id="2ae99-111">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="2ae99-112">ブランドで nontraditional の大文字と小文字の区別が使用されている場合は、通常の名前空間の大文字と小文字が異なる場合でも、ブランドで定義されている大文字と小文字を</span><span class="sxs-lookup"><span data-stu-id="2ae99-112">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="2ae99-113">✔️、必要に応じて複数形の名前空間を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-113">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="2ae99-114">たとえば、`System.Collection` の代わりに `System.Collections` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-114">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="2ae99-115">ただし、ブランド名と頭字語は、このルールの例外です。</span><span class="sxs-lookup"><span data-stu-id="2ae99-115">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="2ae99-116">たとえば、`System.IOs` の代わりに `System.IO` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-116">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="2ae99-117">❌ 名前空間とその名前空間の型に同じ名前を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-117">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="2ae99-118">たとえば、名前空間名として `Debug` を使用せずに、同じ名前空間に `Debug` という名前のクラスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-118">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="2ae99-119">いくつかのコンパイラでは、このような型を完全に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae99-119">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="2ae99-120">名前空間と型名の競合</span><span class="sxs-lookup"><span data-stu-id="2ae99-120">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="2ae99-121">❌ には、`Element`、`Node`、`Log`、`Message`などのジェネリック型名を導入しないでください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-121">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="2ae99-122">これを行うと、一般的なシナリオでの型名の競合が発生する可能性が非常に高くなります。</span><span class="sxs-lookup"><span data-stu-id="2ae99-122">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="2ae99-123">ジェネリック型名 (`FormElement`、`XmlNode`、`EventLog`、`SoapMessage`) を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae99-123">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="2ae99-124">名前空間のカテゴリごとに型名の競合を回避するための特定のガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="2ae99-124">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="2ae99-125">**アプリケーションモデルの名前空間**</span><span class="sxs-lookup"><span data-stu-id="2ae99-125">**Application model namespaces**</span></span>

     <span data-ttu-id="2ae99-126">1つのアプリケーションモデルに属する名前空間は、一緒に使用されることがよくありますが、他のアプリケーションモデルの名前空間で使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-126">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="2ae99-127">たとえば、<xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、<xref:System.Web.UI?displayProperty=nameWithType> 名前空間と一緒に使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-127">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2ae99-128">既知のアプリケーションモデル名前空間グループの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-128">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="2ae99-129">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="2ae99-129">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="2ae99-130">❌、1つのアプリケーションモデル内の名前空間の型に同じ名前を付けません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-130">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="2ae99-131">たとえば、<xref:System.Web.UI?displayProperty=nameWithType> 名前空間には `Page`という名前の型が既に含まれているため、`Page` という名前の型を <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 名前空間に追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-131">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="2ae99-132">**インフラストラクチャの名前空間**</span><span class="sxs-lookup"><span data-stu-id="2ae99-132">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="2ae99-133">このグループには、一般的なアプリケーションの開発時にインポートされることがほとんどない名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ae99-133">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="2ae99-134">たとえば、`.Design` 名前空間は、主にプログラミングツールを開発するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-134">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="2ae99-135">これらの名前空間の型との競合を回避することは、重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-135">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="2ae99-136">**コア名前空間**</span><span class="sxs-lookup"><span data-stu-id="2ae99-136">**Core namespaces**</span></span>

     <span data-ttu-id="2ae99-137">コア名前空間には、アプリケーションモデルの名前空間とインフラストラクチャの名前空間を除く、すべての `System` 名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-137">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="2ae99-138">コア名前空間には、他の、`System`、`System.IO`、`System.Xml`、および `System.Net`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-138">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="2ae99-139">❌ は、コア名前空間の任意の型と競合する型名を指定しません。</span><span class="sxs-lookup"><span data-stu-id="2ae99-139">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="2ae99-140">たとえば、型名として `Stream` を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-140">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="2ae99-141">これは、よく使用される型 <xref:System.IO.Stream?displayProperty=nameWithType>と競合します。</span><span class="sxs-lookup"><span data-stu-id="2ae99-141">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="2ae99-142">**テクノロジ名前空間グループ**</span><span class="sxs-lookup"><span data-stu-id="2ae99-142">**Technology namespace groups**</span></span>

     <span data-ttu-id="2ae99-143">このカテゴリには、`Microsoft.Build.Utilities` や `Microsoft.Build.Tasks`など、`(<Company>.<Technology>*`) と同じ最初の2つの名前空間ノードを持つすべての名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ae99-143">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="2ae99-144">1つのテクノロジに属する型が互いに競合しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="2ae99-144">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="2ae99-145">❌、1つのテクノロジ内の他の型と競合する型名を割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="2ae99-145">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="2ae99-146">❌、テクノロジ名前空間の型とアプリケーションモデルの名前空間の間で型名の競合が発生しないようにします (テクノロジがアプリケーションモデルで使用されることを想定していない場合)。</span><span class="sxs-lookup"><span data-stu-id="2ae99-146">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="2ae99-147">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="2ae99-147">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2ae99-148">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="2ae99-148">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2ae99-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ae99-149">See also</span></span>

- [<span data-ttu-id="2ae99-150">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2ae99-150">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2ae99-151">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2ae99-151">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
