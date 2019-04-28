---
title: 仮想メンバー
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 4943ddcdf1bc4e3e32c8d664cbcc5c50ae3959bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778708"
---
# <a name="virtual-members"></a><span data-ttu-id="57fd7-102">仮想メンバー</span><span class="sxs-lookup"><span data-stu-id="57fd7-102">Virtual Members</span></span>
<span data-ttu-id="57fd7-103">そのため、サブクラスの動作を変更する仮想メンバーをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="57fd7-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="57fd7-104">それらは、それらのもたらす拡張性の観点からのコールバックとよく似ていますが、実行のパフォーマンスとメモリ消費量の観点からは優れています。</span><span class="sxs-lookup"><span data-stu-id="57fd7-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="57fd7-105">また、仮想メンバー自然に感じられる特殊な既存の型 (特殊化) の種類を作成する必要のあるシナリオでします。</span><span class="sxs-lookup"><span data-stu-id="57fd7-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="57fd7-106">仮想メンバーはコールバックとイベントをよりパフォーマンスが向上しますが、非仮想メソッドよりも優れた実行しません。</span><span class="sxs-lookup"><span data-stu-id="57fd7-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="57fd7-107">仮想メンバーの主な欠点は、仮想メンバーの動作はコンパイル時にのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="57fd7-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="57fd7-108">実行時に、コールバックの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="57fd7-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="57fd7-109">コールバック (およびそれよりコールバックの他の情報) などの仮想メンバーを設計、テスト、および仮想メンバーへの呼び出しが予期しない方法でオーバーライドでき、任意のコードを実行できるので、管理コストがかかります。</span><span class="sxs-lookup"><span data-stu-id="57fd7-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="57fd7-110">また、さらに多くの労力は通常、設計と、それらを文書化のコストが高いため、仮想メンバーのコントラクトを明確に定義する必要です。</span><span class="sxs-lookup"><span data-stu-id="57fd7-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="57fd7-111">**X DO NOT** これを行うには相応の理由があり、デザイン、テスト、および仮想メンバーを保守に関連するすべてのコストを認識している限り、メンバーを仮想にすることです。</span><span class="sxs-lookup"><span data-stu-id="57fd7-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="57fd7-112">仮想メンバーは、互換性の問題なしに作成できる変更の観点からありました。</span><span class="sxs-lookup"><span data-stu-id="57fd7-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="57fd7-113">また、これらは、非仮想メンバーよりも低速仮想メンバーへの呼び出しがインラインでないため、ほとんどの場合です。</span><span class="sxs-lookup"><span data-stu-id="57fd7-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="57fd7-114">**✓ CONSIDER** に何がどうしても必要なだけの機能拡張を制限します。</span><span class="sxs-lookup"><span data-stu-id="57fd7-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="57fd7-115">**✓ DO** 仮想メンバーのアクセシビリティは public で保護されたアクセシビリティを優先します。</span><span class="sxs-lookup"><span data-stu-id="57fd7-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="57fd7-116">パブリック メンバーが拡張機能を提供 (必要な) 場合プロテクト仮想メンバーを呼び出すことによって。</span><span class="sxs-lookup"><span data-stu-id="57fd7-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="57fd7-117">クラスのパブリック メンバーは、そのクラスの直接のコンシューマー向けの機能の適切なセットを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fd7-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="57fd7-118">仮想メンバーは、サブクラスで上書きするように設計し、保護されたアクセシビリティが使用する場所のすべての仮想機能拡張ポイントをスコープする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="57fd7-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="57fd7-119">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="57fd7-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="57fd7-120">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="57fd7-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fd7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="57fd7-121">See also</span></span>

- [<span data-ttu-id="57fd7-122">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="57fd7-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="57fd7-123">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="57fd7-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
