---
title: 抽象化 (抽象型およびインターフェイス)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: KrzysztofCwalina
ms.openlocfilehash: fcf566c24677630fdbb1fcd0eb7628f830b3be2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789221"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="9c386-102">抽象化 (抽象型およびインターフェイス)</span><span class="sxs-lookup"><span data-stu-id="9c386-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="9c386-103">抽象化は、コントラクトを記述するコントラクトの完全な実装を提供しない型です。</span><span class="sxs-lookup"><span data-stu-id="9c386-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="9c386-104">抽象化は通常インターフェイスまたは抽象クラスとして実装し、適切に定義された一連のコントラクトを実装する型の必要なセマンティクスを説明するリファレンス ドキュメントが付属します。</span><span class="sxs-lookup"><span data-stu-id="9c386-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="9c386-105">.NET Framework で最も重要な抽象化のものが<xref:System.IO.Stream>、 <xref:System.Collections.Generic.IEnumerable%601>、および<xref:System.Object>します。</span><span class="sxs-lookup"><span data-stu-id="9c386-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="9c386-106">抽象化のコントラクトをサポートする具象型を実装して、フレームワーク Api がかかる (操作) でこの具象型を使用してフレームワークを拡張することができます、抽象化します。</span><span class="sxs-lookup"><span data-stu-id="9c386-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="9c386-107">時の試練に耐え得ることが有意義で便利な抽象化は、設計することは困難です。</span><span class="sxs-lookup"><span data-stu-id="9c386-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="9c386-108">メインの難しさがなくなると不要な少なく、メンバーの適切なセットを取得しています。</span><span class="sxs-lookup"><span data-stu-id="9c386-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="9c386-109">抽象化のメンバーが多すぎる場合は、難しいかを実装することが不可能になります。</span><span class="sxs-lookup"><span data-stu-id="9c386-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="9c386-110">約束の機能が少なすぎますメンバー場合は、多くの興味深いシナリオで役に立たないになります。</span><span class="sxs-lookup"><span data-stu-id="9c386-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="9c386-111">フレームワークで多くの抽象化には、フレームワークの使いやすさも悪影響に影響します。</span><span class="sxs-lookup"><span data-stu-id="9c386-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="9c386-112">多くの場合、具体的な実装と抽象化で動作している Api の大きい画像に組み込む方法を理解せず、抽象化を理解することが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="9c386-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="9c386-113">また、抽象化とそのメンバーの名前は必ずしも抽象頻繁なものになりますわかりにくいと印象は最初の使用量のより広範なコンテキストを理解することがなく。</span><span class="sxs-lookup"><span data-stu-id="9c386-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="9c386-114">ただし、抽象化は、その他の拡張メカニズムは、できない多くの場合と一致する非常に強力な機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c386-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="9c386-115">多くのアーキテクチャ パターン、プラグインなどの中核には制御の反転 (IoC)、パイプライン、やなど。</span><span class="sxs-lookup"><span data-stu-id="9c386-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="9c386-116">フレームワークのテストの容易性の非常に重要なもいます。</span><span class="sxs-lookup"><span data-stu-id="9c386-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="9c386-117">適切な抽象化を使用すれば、単体テストするために大量の依存関係を消去できます。</span><span class="sxs-lookup"><span data-stu-id="9c386-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="9c386-118">要約すると、抽象化は、最新のオブジェクト指向フレームワークのいる豊富な機能を担当します。</span><span class="sxs-lookup"><span data-stu-id="9c386-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="9c386-119">**X DO NOT** いくつかの具体的な実装と、抽象化を使用する Api を開発してテストする場合を除き、抽象化を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c386-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="9c386-120">**✓ DO** 抽象化を設計するときは、抽象クラスとインターフェイス間慎重に選択します。</span><span class="sxs-lookup"><span data-stu-id="9c386-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="9c386-121">**✓ CONSIDER** 抽象クラスの具象実装のテストの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c386-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="9c386-122">このようなテストは、その実装が正しく、コントラクトを実装するかどうかをテストするユーザーを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c386-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="9c386-123">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="9c386-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c386-124">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="9c386-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c386-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c386-125">See also</span></span>

- [<span data-ttu-id="9c386-126">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9c386-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="9c386-127">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="9c386-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
