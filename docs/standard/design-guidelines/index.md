---
title: フレームワーク デザインのガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: c20430f9cdcd71cc2e178d38aeed48f9fa4e75c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026381"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="014be-102">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-102">Framework Design Guidelines</span></span>
<span data-ttu-id="014be-103">このセクションでは、ライブラリを拡張し、.NET Framework との対話を設計するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="014be-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="014be-104">目標は、ライブラリの設計者は開発のために使用するプログラミング言語の独立した統一プログラミング モデルを提供することで API の一貫性と使いやすさを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="014be-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="014be-105">.NET Framework を拡張するクラスやコンポーネントを開発する際に、これらのデザイン ガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="014be-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="014be-106">一貫性のないライブラリ デザインが悪影響を及ぼす開発者の生産性に影響し、導入を抑制します。</span><span class="sxs-lookup"><span data-stu-id="014be-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="014be-107">ガイドラインは言葉を使った簡単な推奨事項として編成されて`Do`、 `Consider`、 `Avoid`、および`Do not`します。</span><span class="sxs-lookup"><span data-stu-id="014be-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="014be-108">次のガイドラインの目的は、クラス ライブラリのデザイナーのさまざまなソリューション間のトレードオフを理解します。</span><span class="sxs-lookup"><span data-stu-id="014be-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="014be-109">優れたライブラリ デザインのこれらのデザイン ガイドラインに違反することが必要な場所の状況である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="014be-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="014be-110">このような場合はまれで、する必要があります、意思決定の理由を明確かつ説得力のあることが重要です。</span><span class="sxs-lookup"><span data-stu-id="014be-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="014be-111">次のガイドライン、ブックからの抜粋は*Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリでは、2 nd Edition のパターン*Krzysztof Cwalina、Brad 内容。</span><span class="sxs-lookup"><span data-stu-id="014be-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="014be-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="014be-112">In This Section</span></span>  
 [<span data-ttu-id="014be-113">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="014be-114">アセンブリ、名前空間、型、およびクラス ライブラリ内のメンバーの名前付けのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="014be-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="014be-115">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="014be-116">静的な抽象クラス、インターフェイス、列挙型、構造、およびその他の種類を使用するためのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="014be-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="014be-117">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="014be-118">設計とプロパティ、メソッド、コンス トラクター、フィールド、イベント、演算子、およびパラメーターの使用に関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="014be-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="014be-119">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="014be-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="014be-120">イベントや仮想メンバーは、コールバック関数を使用して、サブクラス化などの拡張メカニズムについて説明し、フレームワークの要件に最適なメカニズムを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="014be-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="014be-121">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="014be-122">デザイン、スロー、および例外をキャッチのデザイン ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="014be-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="014be-123">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="014be-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="014be-124">配列、属性、およびコレクションなどの一般的な型を使用して、シリアル化のサポート、等値演算子のオーバー ロードするためのガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="014be-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="014be-125">共通デザイン パターン</span><span class="sxs-lookup"><span data-stu-id="014be-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="014be-126">選択して、依存関係プロパティを実装するためのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="014be-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="014be-127">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="014be-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="014be-128">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="014be-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014be-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="014be-129">See also</span></span>

- [<span data-ttu-id="014be-130">概要</span><span class="sxs-lookup"><span data-stu-id="014be-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="014be-131">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="014be-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
