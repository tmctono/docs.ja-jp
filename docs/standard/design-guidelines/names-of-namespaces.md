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
author: KrzysztofCwalina
ms.openlocfilehash: b8b6ec195fd3f95a4255ea820f2bffcb3e27ba19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615216"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="44fc5-102">名前空間の名前</span><span class="sxs-lookup"><span data-stu-id="44fc5-102">Names of Namespaces</span></span>
<span data-ttu-id="44fc5-103">として他の名前付けのガイドラインと名前空間の名前を付けるときの目標を作成するための十分なわかりやすくするために名前空間のコンテンツがある可能性がありますをすぐにいるフレームワークを使用するプログラマにとって。</span><span class="sxs-lookup"><span data-stu-id="44fc5-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="44fc5-104">次のテンプレートは、名前空間の名前付けに関する一般的な規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="44fc5-105">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="44fc5-106">**✓ DO** から同じ名前を持つ異なる会社から名前空間を防ぐために、会社名と名前空間名をプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="44fc5-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="44fc5-107">**✓ DO** 名前空間の名前の 2 番目のレベルで、安定したバージョンに依存しない製品名を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="44fc5-108">**X DO NOT** 企業内のグループ名は、短時間である傾向があるため、名前空間の階層内の名前の基準として組織階層を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="44fc5-109">関連するテクノロジのグループの周囲の名前空間の階層を整理します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="44fc5-110">**✓ DO** をピリオド pascal 表記を使用、および別の名前空間のコンポーネントを使用して (例: `Microsoft.Office.PowerPoint`)。</span><span class="sxs-lookup"><span data-stu-id="44fc5-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="44fc5-111">ブランドは、従来とは異なる大文字小文字の区別を使用している場合は、名前空間の通常の文字種から以上逸脱している場合でも、ブランド名で定義されている大文字小文字の区別に従ってください。</span><span class="sxs-lookup"><span data-stu-id="44fc5-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="44fc5-112">**✓ CONSIDER** 適切な場所に複数形の名前空間の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="44fc5-113">たとえば、`System.Collection` の代わりに `System.Collections` を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="44fc5-114">ブランド名や略語は、この規則の例外をただしです。</span><span class="sxs-lookup"><span data-stu-id="44fc5-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="44fc5-115">たとえば、`System.IOs` の代わりに `System.IO` を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="44fc5-116">**X DO NOT** その名前空間、名前空間と型に同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="44fc5-117">たとえば、使用しないでください`Debug`、名前空間と名前を指定し、という名前のクラスも提供`Debug`同じ名前空間。</span><span class="sxs-lookup"><span data-stu-id="44fc5-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="44fc5-118">いくつかのコンパイラでは、このような型を完全に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44fc5-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="44fc5-119">名前空間と型名の競合</span><span class="sxs-lookup"><span data-stu-id="44fc5-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="44fc5-120">**X DO NOT** など、ジェネリック型の名前を導入`Element`、 `Node`、 `Log`、および`Message`です。</span><span class="sxs-lookup"><span data-stu-id="44fc5-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="44fc5-121">名前を入力すると、そう競合シナリオで共通の非常に高い確率があります。</span><span class="sxs-lookup"><span data-stu-id="44fc5-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="44fc5-122">ジェネリック型の名前を修飾する必要があります (`FormElement`、 `XmlNode`、 `EventLog`、 `SoapMessage`)。</span><span class="sxs-lookup"><span data-stu-id="44fc5-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="44fc5-123">異なるカテゴリの名前空間の型名の競合を回避するための特定のガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="44fc5-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="44fc5-124">**アプリケーション モデルの名前空間**</span><span class="sxs-lookup"><span data-stu-id="44fc5-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="44fc5-125">1 つのアプリケーション モデルに属している名前空間が同時に、使用される非常に多くの場合がほとんどない他のアプリケーション モデルの名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="44fc5-126">たとえば、<xref:System.Windows.Forms?displayProperty=nameWithType>と共に名前空間が使用される非常にまれ、<xref:System.Web.UI?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="44fc5-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="44fc5-127">よく知られたアプリケーション モデルの名前空間のグループの一覧を次には。</span><span class="sxs-lookup"><span data-stu-id="44fc5-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="44fc5-128">**X DO NOT** 1 つのアプリケーション モデル内の名前空間の型に同じ名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="44fc5-129">たとえば、という名前の型を追加しないでください`Page`に、<xref:System.Web.UI.Adapters?displayProperty=nameWithType>名前空間、ため、<xref:System.Web.UI?displayProperty=nameWithType>名前空間に既にという名前の型が含まれている`Page`。</span><span class="sxs-lookup"><span data-stu-id="44fc5-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="44fc5-130">**インフラストラクチャの名前空間**</span><span class="sxs-lookup"><span data-stu-id="44fc5-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="44fc5-131">このグループには、ほとんどの一般的なアプリケーションの開発時にインポートされる名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44fc5-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="44fc5-132">たとえば、`.Design`プログラミングの開発ツールと名前空間は主に使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="44fc5-133">これらの名前空間内の型との競合を避けるは重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="44fc5-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="44fc5-134">**コア名前空間**</span><span class="sxs-lookup"><span data-stu-id="44fc5-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="44fc5-135">すべてのコア名前空間を含める`System`アプリケーション モデルの名前空間およびインフラストラクチャの名前空間を除く、名前空間。</span><span class="sxs-lookup"><span data-stu-id="44fc5-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="44fc5-136">その他のコア名前空間が含まれます`System`、 `System.IO`、 `System.Xml`、および`System.Net`します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="44fc5-137">**X DO NOT** 付与がコア名前空間の型と競合する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="44fc5-138">たとえば、使用しないでください`Stream`型名として。</span><span class="sxs-lookup"><span data-stu-id="44fc5-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="44fc5-139">競合する<xref:System.IO.Stream?displayProperty=nameWithType>、非常によく型を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="44fc5-140">**テクノロジの名前空間のグループ**</span><span class="sxs-lookup"><span data-stu-id="44fc5-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="44fc5-141">このカテゴリには、同じ最初の 2 つの名前空間ノードを持つすべての名前空間が含まれています。 `(<Company>.<Technology>*`)、など`Microsoft.Build.Utilities`と`Microsoft.Build.Tasks`します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="44fc5-142">1 つのテクノロジに属している型が互いに競合しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="44fc5-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="44fc5-143">**X DO NOT** 1 つのテクノロジ内の他の種類と競合する型の名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="44fc5-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="44fc5-144">**X DO NOT** (場合を除く、テクノロジは、アプリケーション モデルで使用するものではありません) テクノロジの名前空間の型と、アプリケーション モデルの名前空間の型名の競合を紹介します。</span><span class="sxs-lookup"><span data-stu-id="44fc5-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="44fc5-145">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="44fc5-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="44fc5-146">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="44fc5-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fc5-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="44fc5-147">See also</span></span>

- [<span data-ttu-id="44fc5-148">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="44fc5-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="44fc5-149">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="44fc5-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
