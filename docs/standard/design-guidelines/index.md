---
title: フレームワーク デザインのガイドライン
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 5a4edca70844a2b2a3972381b34efe85664f353d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276037"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="1982c-102">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-102">Framework Design Guidelines</span></span>
<span data-ttu-id="1982c-103">このセクションでは、.NET Framework を拡張および操作するライブラリを設計するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="1982c-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="1982c-104">この目標は、開発に使用されるプログラミング言語に依存しない統合プログラミングモデルを提供することで、ライブラリデザイナーが API の一貫性と使いやすさを保証できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="1982c-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="1982c-105">.NET Framework を拡張するクラスおよびコンポーネントを開発する場合は、これらのデザインガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1982c-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="1982c-106">一貫性のないライブラリ設計は、開発者の生産性に悪影響を及ぼし、導入を推奨しません。</span><span class="sxs-lookup"><span data-stu-id="1982c-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="1982c-107">ガイドラインは、「」、「」、および「」という用語で構成される単純な推奨事項としてまとめられてい `Do` `Consider` `Avoid` `Do not` ます。</span><span class="sxs-lookup"><span data-stu-id="1982c-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="1982c-108">これらのガイドラインは、クラスライブラリデザイナーがさまざまなソリューション間のトレードオフを理解できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="1982c-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="1982c-109">優れたライブラリ設計では、これらの設計ガイドラインに違反することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1982c-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="1982c-110">このようなケースはまれであり、明確で説得力のある理由を決定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1982c-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="1982c-111">これらのガイドラインは、抜粋です*Framework の設計ガイドラインから、再利用可能な .Net ライブラリである2番目のエディション*(Krzysztof Cwalina と Brad abrams) の規則、表現、パターンについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="1982c-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1982c-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1982c-112">In This Section</span></span>  
 [<span data-ttu-id="1982c-113">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-113">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="1982c-114">クラスライブラリのアセンブリ、名前空間、型、およびメンバーの名前付けに関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="1982c-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="1982c-115">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-115">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="1982c-116">静的クラス、抽象クラス、インターフェイス、列挙体、構造体、およびその他の型を使用するためのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="1982c-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="1982c-117">メンバーデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-117">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="1982c-118">プロパティ、メソッド、コンストラクター、フィールド、イベント、演算子、およびパラメーターのデザインと使用に関するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="1982c-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="1982c-119">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="1982c-119">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="1982c-120">サブクラス化、イベント、仮想メンバー、コールバックなどの拡張機能について説明し、フレームワークの要件に最も適したメカニズムを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1982c-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="1982c-121">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-121">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="1982c-122">例外をデザイン、スロー、キャッチするためのデザインガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1982c-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="1982c-123">使用に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="1982c-123">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="1982c-124">配列、属性、コレクションなどの共通型の使用、シリアル化のサポート、および等値演算子のオーバーロードに関するガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1982c-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="1982c-125">一般的なデザインパターン</span><span class="sxs-lookup"><span data-stu-id="1982c-125">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="1982c-126">依存関係プロパティの選択と実装に関するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="1982c-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="1982c-127">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="1982c-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1982c-128">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="1982c-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1982c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1982c-129">See also</span></span>

- [<span data-ttu-id="1982c-130">概要</span><span class="sxs-lookup"><span data-stu-id="1982c-130">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="1982c-131">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="1982c-131">Development Guide</span></span>](../../framework/development-guide.md)
