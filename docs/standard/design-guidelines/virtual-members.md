---
title: 仮想メンバー
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 2c1e6d9aeafa1c9d7ee4b0c2c626b6fd7be6cf99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708972"
---
# <a name="virtual-members"></a><span data-ttu-id="4afb7-102">仮想メンバー</span><span class="sxs-lookup"><span data-stu-id="4afb7-102">Virtual Members</span></span>
<span data-ttu-id="4afb7-103">仮想メンバーをオーバーライドして、サブクラスの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4afb7-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="4afb7-104">これらの関数は、提供される機能拡張に関してコールバックとよく似ていますが、実行のパフォーマンスとメモリの消費に関しては優れています。</span><span class="sxs-lookup"><span data-stu-id="4afb7-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="4afb7-105">また、仮想メンバーは、特別な種類の既存の型 (特殊化) を作成する必要があるシナリオでは、より自然に感じられます。</span><span class="sxs-lookup"><span data-stu-id="4afb7-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="4afb7-106">仮想メンバーは、コールバックとイベントよりもパフォーマンスが優れていますが、非仮想メソッドよりもパフォーマンスは高くありません。</span><span class="sxs-lookup"><span data-stu-id="4afb7-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="4afb7-107">仮想メンバーの主な欠点は、仮想メンバーの動作は、コンパイル時にのみ変更できることです。</span><span class="sxs-lookup"><span data-stu-id="4afb7-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="4afb7-108">コールバックの動作は、実行時に変更できます。</span><span class="sxs-lookup"><span data-stu-id="4afb7-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="4afb7-109">仮想メンバーは、コールバック (またはコールバックを超える可能性があります) のように、設計、テスト、および保守にコストがかかります。これは、仮想メンバーへの呼び出しを予測不可能な方法でオーバーライドし、任意のコードを実行できるためです。</span><span class="sxs-lookup"><span data-stu-id="4afb7-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="4afb7-110">また、仮想メンバーのコントラクトを明確に定義するために、通常はより多くの労力が必要になります。そのため、これらを設計および文書化するコストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="4afb7-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="4afb7-111">**X DO NOT** これを行うには相応の理由があり、デザイン、テスト、および仮想メンバーを保守に関連するすべてのコストを認識している限り、メンバーを仮想にすることです。</span><span class="sxs-lookup"><span data-stu-id="4afb7-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="4afb7-112">仮想メンバーは、互換性を損なうことなく変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4afb7-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="4afb7-113">また、仮想メンバーへの呼び出しはインライン化されないため、ほとんどの場合、仮想メンバー以外のメンバーよりも低速になります。</span><span class="sxs-lookup"><span data-stu-id="4afb7-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="4afb7-114">**✓ CONSIDER** に何がどうしても必要なだけの機能拡張を制限します。</span><span class="sxs-lookup"><span data-stu-id="4afb7-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="4afb7-115">**✓ DO** 仮想メンバーのアクセシビリティは public で保護されたアクセシビリティを優先します。</span><span class="sxs-lookup"><span data-stu-id="4afb7-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="4afb7-116">パブリックメンバーは、保護された仮想メンバーを呼び出すことによって、拡張機能を提供する必要があります (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="4afb7-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="4afb7-117">クラスのパブリックメンバーは、そのクラスの直接のコンシューマーに適切な一連の機能を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afb7-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="4afb7-118">仮想メンバーはサブクラスでオーバーライドされるように設計されており、保護されたアクセシビリティは、すべての仮想拡張ポイントを使用できる場所にスコープを設定するための優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="4afb7-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="4afb7-119">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="4afb7-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4afb7-120">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="4afb7-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afb7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4afb7-121">See also</span></span>

- [<span data-ttu-id="4afb7-122">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="4afb7-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4afb7-123">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="4afb7-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
