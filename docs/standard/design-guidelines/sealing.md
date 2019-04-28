---
title: シール
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: KrzysztofCwalina
ms.openlocfilehash: c8aeb5ce3d93755f30bf68732592a08d7af54957
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762063"
---
# <a name="sealing"></a><span data-ttu-id="50428-102">シール</span><span class="sxs-lookup"><span data-stu-id="50428-102">Sealing</span></span>
<span data-ttu-id="50428-103">オブジェクト指向フレームワークの機能の 1 つは、開発者が拡張およびフレームワークの設計者によって予期しない方法でそれらをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="50428-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="50428-104">これは、両方の電源および拡張可能なデザインの危険性。</span><span class="sxs-lookup"><span data-stu-id="50428-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="50428-105">フレームワークを設計するときは、そのため、慎重に拡張機能の設計が必要なときに危険な場合は、機能拡張を制限して、非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="50428-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="50428-106">機能拡張を防ぐ強力なメカニズムをシールします。</span><span class="sxs-lookup"><span data-stu-id="50428-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="50428-107">クラスまたは個々 のメンバーをシールすることができます。</span><span class="sxs-lookup"><span data-stu-id="50428-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="50428-108">クラスをシールすると、ユーザーがクラスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="50428-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="50428-109">メンバーをシールすると、ユーザーが特定のメンバーをオーバーライドできなくなります。</span><span class="sxs-lookup"><span data-stu-id="50428-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="50428-110">**X DO NOT** これを行うには相応の理由をしなくてもクラスをシールします。</span><span class="sxs-lookup"><span data-stu-id="50428-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="50428-111">機能拡張シナリオを考えることはできませんので、クラスをシールすることは正当な理由ではありません。</span><span class="sxs-lookup"><span data-stu-id="50428-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="50428-112">フレームワークのユーザーの利便性のためのメンバーの追加など、さまざまな明確な理由のクラスから継承したいです。</span><span class="sxs-lookup"><span data-stu-id="50428-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="50428-113">参照してください[封印されていないクラス](../../../docs/standard/design-guidelines/unsealed-classes.md)明確な理由の例については、ユーザーが型から継承するようにします。</span><span class="sxs-lookup"><span data-stu-id="50428-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="50428-114">クラスをシールする理由を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="50428-114">Good reasons for sealing a class include the following:</span></span>  
  
- <span data-ttu-id="50428-115">クラスは、静的クラスです。</span><span class="sxs-lookup"><span data-stu-id="50428-115">The class is a static class.</span></span> <span data-ttu-id="50428-116">参照してください[静的クラスのデザイン](../../../docs/standard/design-guidelines/static-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="50428-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
- <span data-ttu-id="50428-117">クラスは、継承されたプロテクト メンバーのセキュリティに重要なシークレットを格納します。</span><span class="sxs-lookup"><span data-stu-id="50428-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
- <span data-ttu-id="50428-118">クラスは、多くの仮想メンバーを継承し、それらを個別にシールのコストは封印されていないクラスを離れることのメリットを上回ります。 します。</span><span class="sxs-lookup"><span data-stu-id="50428-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
- <span data-ttu-id="50428-119">クラスは、非常に高速なランタイム参照が必要な属性です。</span><span class="sxs-lookup"><span data-stu-id="50428-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="50428-120">Sealed 属性では、封印されていないものよりもわずかに高いパフォーマンス レベルがあります。</span><span class="sxs-lookup"><span data-stu-id="50428-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="50428-121">参照してください[属性](../../../docs/standard/design-guidelines/attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="50428-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="50428-122">**X DO NOT** sealed 型でプロテクト メンバーまたは仮想メンバーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="50428-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="50428-123">定義上、sealed 型から継承できません。</span><span class="sxs-lookup"><span data-stu-id="50428-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="50428-124">つまり、sealed 型でプロテクト メンバーを呼び出すことはできません、および、sealed 型での仮想メソッドをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="50428-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="50428-125">**✓ CONSIDER** をオーバーライドするメンバーをシールします。</span><span class="sxs-lookup"><span data-stu-id="50428-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="50428-126">仮想メンバーの概要に起因する問題 (で説明した[仮想メンバー](../../../docs/standard/design-guidelines/virtual-members.md)) やや劣る度にも同様に、上書きを適用します。</span><span class="sxs-lookup"><span data-stu-id="50428-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="50428-127">オーバーライドをシール、継承階層の時点からこれらの問題から保護します。</span><span class="sxs-lookup"><span data-stu-id="50428-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="50428-128">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="50428-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="50428-129">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="50428-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50428-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="50428-130">See also</span></span>

- [<span data-ttu-id="50428-131">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="50428-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="50428-132">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="50428-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="50428-133">シールされていないクラス</span><span class="sxs-lookup"><span data-stu-id="50428-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
