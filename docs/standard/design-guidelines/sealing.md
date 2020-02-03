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
ms.openlocfilehash: ddf463e98fb6a9c5ccaae90e9cfc74b5691b13a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743626"
---
# <a name="sealing"></a><span data-ttu-id="ea834-102">シール</span><span class="sxs-lookup"><span data-stu-id="ea834-102">Sealing</span></span>
<span data-ttu-id="ea834-103">オブジェクト指向フレームワークの機能の1つは、開発者がフレームワークデザイナーによって予期されない方法で拡張およびカスタマイズできることです。</span><span class="sxs-lookup"><span data-stu-id="ea834-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="ea834-104">これは、拡張可能な設計の力と危険性の両方です。</span><span class="sxs-lookup"><span data-stu-id="ea834-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="ea834-105">フレームワークを設計するときは、必要に応じて拡張機能を慎重に設計し、危険な場合には拡張性を制限することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="ea834-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="ea834-106">拡張性を防ぐための強力なメカニズムが封印されています。</span><span class="sxs-lookup"><span data-stu-id="ea834-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="ea834-107">クラスまたは個々のメンバーを封印できます。</span><span class="sxs-lookup"><span data-stu-id="ea834-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="ea834-108">クラスをシールすると、ユーザーはクラスから継承できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea834-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="ea834-109">メンバーを封印すると、ユーザーは特定のメンバーをオーバーライドできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea834-109">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="ea834-110">❌ は、適切な理由がなくてもクラスを封印しないでください。</span><span class="sxs-lookup"><span data-stu-id="ea834-110">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="ea834-111">拡張シナリオを考慮することができないため、クラスをシールすることは適切な理由ではありません。</span><span class="sxs-lookup"><span data-stu-id="ea834-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="ea834-112">利便性のあるメンバーを追加するなど、さまざまな理由からクラスを継承しようとしているフレームワークユーザー。</span><span class="sxs-lookup"><span data-stu-id="ea834-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="ea834-113">ユーザーが型から継承することを望まない明確な理由の例については、「封印されていない[クラス](../../../docs/standard/design-guidelines/unsealed-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea834-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="ea834-114">クラスを封印するには、次のような理由があります。</span><span class="sxs-lookup"><span data-stu-id="ea834-114">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="ea834-115">クラスは静的クラスです。</span><span class="sxs-lookup"><span data-stu-id="ea834-115">The class is a static class.</span></span> <span data-ttu-id="ea834-116">「[静的クラスの設計](../../../docs/standard/design-guidelines/static-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea834-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>

- <span data-ttu-id="ea834-117">クラスは、セキュリティに依存する機密情報を継承されたメンバーに格納します。</span><span class="sxs-lookup"><span data-stu-id="ea834-117">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="ea834-118">クラスは多くの仮想メンバーを継承し、それらを個別にシールするコストは、クラスをシールしたままにする利点よりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="ea834-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="ea834-119">クラスは、非常に高速なランタイム参照を必要とする属性です。</span><span class="sxs-lookup"><span data-stu-id="ea834-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="ea834-120">シールされた属性のパフォーマンスレベルは、封印されていない属性よりも若干高くなります。</span><span class="sxs-lookup"><span data-stu-id="ea834-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="ea834-121">「[属性](../../../docs/standard/design-guidelines/attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea834-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>

 <span data-ttu-id="ea834-122">❌ は、シールド型で protected または virtual メンバーを宣言しません。</span><span class="sxs-lookup"><span data-stu-id="ea834-122">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="ea834-123">定義上、sealed 型をから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea834-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="ea834-124">これは、シールされた型のプロテクトメンバーを呼び出すことができず、シール型の仮想メソッドをオーバーライドできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ea834-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="ea834-125">オーバーライドするメンバーの封印を検討✔️。</span><span class="sxs-lookup"><span data-stu-id="ea834-125">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="ea834-126">仮想メンバーの導入によって発生する可能性のある問題 (「[仮想メンバー](../../../docs/standard/design-guidelines/virtual-members.md)」で説明) は、オーバーライドにも適用されます (ただし、若干低い程度)。</span><span class="sxs-lookup"><span data-stu-id="ea834-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="ea834-127">上書きを封印すると、継承階層内のその時点から、これらの問題を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="ea834-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="ea834-128">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="ea834-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ea834-129">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="ea834-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ea834-130">参照</span><span class="sxs-lookup"><span data-stu-id="ea834-130">See also</span></span>

- [<span data-ttu-id="ea834-131">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="ea834-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="ea834-132">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="ea834-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="ea834-133">シールされていないクラス</span><span class="sxs-lookup"><span data-stu-id="ea834-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
