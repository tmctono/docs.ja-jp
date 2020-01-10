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
ms.openlocfilehash: 0678f695e3ae7c40660031862c9073a21fd72491
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709232"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="a3a0b-102">名前空間の名前</span><span class="sxs-lookup"><span data-stu-id="a3a0b-102">Names of Namespaces</span></span>
<span data-ttu-id="a3a0b-103">他の命名ガイドラインと同様に、名前空間に名前を付ける際の目的は、名前空間の内容がどのようなものである可能性があるかをすぐに把握するために、フレームワークを使用するプログラマにとって十分なわかりやすいものにすることです。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="a3a0b-104">次のテンプレートは、名前空間の名前付けに関する一般的な規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="a3a0b-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="a3a0b-106">**✓ DO** から同じ名前を持つ異なる会社から名前空間を防ぐために、会社名と名前空間名をプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="a3a0b-107">**✓ DO** 名前空間の名前の 2 番目のレベルで、安定したバージョンに依存しない製品名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="a3a0b-108">**X DO NOT** 企業内のグループ名は、短時間である傾向があるため、名前空間の階層内の名前の基準として組織階層を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="a3a0b-109">関連するテクノロジのグループを中心に、名前空間の階層を整理します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="a3a0b-110">**✓ DO** をピリオド pascal 表記を使用、および別の名前空間のコンポーネントを使用して (例: `Microsoft.Office.PowerPoint`)。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="a3a0b-111">ブランドで nontraditional の大文字と小文字の区別が使用されている場合は、通常の名前空間の大文字と小文字が異なる場合でも、ブランドで定義されている大文字と小文字を</span><span class="sxs-lookup"><span data-stu-id="a3a0b-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="a3a0b-112">**✓ CONSIDER** 適切な場所に複数形の名前空間の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="a3a0b-113">たとえば、`System.Collection` の代わりに `System.Collections` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="a3a0b-114">ただし、ブランド名と頭字語は、このルールの例外です。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="a3a0b-115">たとえば、`System.IOs` の代わりに `System.IO` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="a3a0b-116">**X DO NOT** その名前空間、名前空間と型に同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="a3a0b-117">たとえば、名前空間名として `Debug` を使用せずに、同じ名前空間に `Debug` という名前のクラスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="a3a0b-118">いくつかのコンパイラでは、このような型を完全に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="a3a0b-119">名前空間と型名の競合</span><span class="sxs-lookup"><span data-stu-id="a3a0b-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="a3a0b-120">**X DO NOT** など、ジェネリック型の名前を導入`Element`、 `Node`、 `Log`、および`Message`です。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="a3a0b-121">これを行うと、一般的なシナリオでの型名の競合が発生する可能性が非常に高くなります。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="a3a0b-122">ジェネリック型名 (`FormElement`、`XmlNode`、`EventLog`、`SoapMessage`) を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="a3a0b-123">名前空間のカテゴリごとに型名の競合を回避するための特定のガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="a3a0b-124">**アプリケーションモデルの名前空間**</span><span class="sxs-lookup"><span data-stu-id="a3a0b-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="a3a0b-125">1つのアプリケーションモデルに属する名前空間は、一緒に使用されることがよくありますが、他のアプリケーションモデルの名前空間で使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="a3a0b-126">たとえば、<xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、<xref:System.Web.UI?displayProperty=nameWithType> 名前空間と一緒に使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a3a0b-127">既知のアプリケーションモデル名前空間グループの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="a3a0b-128">**X DO NOT** 1 つのアプリケーション モデル内の名前空間の型に同じ名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="a3a0b-129">たとえば、<xref:System.Web.UI?displayProperty=nameWithType> 名前空間には `Page`という名前の型が既に含まれているため、`Page` という名前の型を <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 名前空間に追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="a3a0b-130">**インフラストラクチャの名前空間**</span><span class="sxs-lookup"><span data-stu-id="a3a0b-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="a3a0b-131">このグループには、一般的なアプリケーションの開発時にインポートされることがほとんどない名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="a3a0b-132">たとえば、`.Design` 名前空間は、主にプログラミングツールを開発するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="a3a0b-133">これらの名前空間の型との競合を回避することは、重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="a3a0b-134">**コア名前空間**</span><span class="sxs-lookup"><span data-stu-id="a3a0b-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="a3a0b-135">コア名前空間には、アプリケーションモデルの名前空間とインフラストラクチャの名前空間を除く、すべての `System` 名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="a3a0b-136">コア名前空間には、他の、`System`、`System.IO`、`System.Xml`、および `System.Net`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="a3a0b-137">**X DO NOT** 付与がコア名前空間の型と競合する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="a3a0b-138">たとえば、型名として `Stream` を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="a3a0b-139">これは、よく使用される型 <xref:System.IO.Stream?displayProperty=nameWithType>と競合します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="a3a0b-140">**テクノロジ名前空間グループ**</span><span class="sxs-lookup"><span data-stu-id="a3a0b-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="a3a0b-141">このカテゴリには、`Microsoft.Build.Utilities` や `Microsoft.Build.Tasks`など、`(<Company>.<Technology>*`) と同じ最初の2つの名前空間ノードを持つすべての名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="a3a0b-142">1つのテクノロジに属する型が互いに競合しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="a3a0b-143">**X DO NOT** 1 つのテクノロジ内の他の種類と競合する型の名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="a3a0b-144">**X DO NOT** (場合を除く、テクノロジは、アプリケーション モデルで使用するものではありません) テクノロジの名前空間の型と、アプリケーション モデルの名前空間の型名の競合を紹介します。</span><span class="sxs-lookup"><span data-stu-id="a3a0b-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="a3a0b-145">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a3a0b-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a3a0b-146">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a3a0b-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a0b-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3a0b-147">See also</span></span>

- [<span data-ttu-id="a3a0b-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3a0b-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a3a0b-149">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3a0b-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
