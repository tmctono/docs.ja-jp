---
title: インターフェイスのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: 1f982aa37f92b7270725574d949989ca120297d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026368"
---
# <a name="interface-design"></a><span data-ttu-id="c6268-102">インターフェイスのデザイン</span><span class="sxs-lookup"><span data-stu-id="c6268-102">Interface Design</span></span>
<span data-ttu-id="c6268-103">ほとんどの Api は、クラスと構造体を使用して最適なモデル化、インターフェイスがより適切なまたは唯一のオプションの場合は。</span><span class="sxs-lookup"><span data-stu-id="c6268-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="c6268-104">CLR は多重継承をサポートしていません (つまり、CLR クラスから継承できません 1 つ以上の基底クラス) が、基本クラスから継承するだけでなく、1 つまたは複数のインターフェイスを実装する型。</span><span class="sxs-lookup"><span data-stu-id="c6268-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="c6268-105">そのため、インターフェイスは、多重継承の効果を実現するためによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6268-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="c6268-106">たとえば、<xref:System.IDisposable>は参加する継承階層の独立した disposability をサポートする型を許可するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c6268-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="c6268-107">他のどの定義で、インターフェイスは、適切な状況がいくつかの値の型を含む複数の種類でサポートされる共通のインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6268-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="c6268-108">値の型が以外の型から継承できません<xref:System.ValueType>、共通の基本型を提供するために、唯一のオプションは、インターフェイスを使用して、インターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="c6268-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="c6268-109">**✓ DO** いくつかの一般的な API 値の型を含む型のセットでサポートする必要がある場合は、インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6268-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="c6268-110">**✓ CONSIDER** 既に他の型を継承する型でその機能をサポートする必要がある場合は、インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6268-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="c6268-111">**X AVOID** マーカー インターフェイス (メンバーを持たないインターフェイス) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6268-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="c6268-112">特定の特性 (マーカー) を持つものとしてマークする必要がある場合は、一般に、インターフェイスではなく、カスタム属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6268-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="c6268-113">**✓ DO** インターフェイスの実装は、少なくとも 1 つの型を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6268-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="c6268-114">インターフェイスのデザインを検証するには、この支援を行っています。</span><span class="sxs-lookup"><span data-stu-id="c6268-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="c6268-115">たとえば、<xref:System.Collections.Generic.List%601>の実装には、<xref:System.Collections.Generic.IList%601>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c6268-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="c6268-116">**✓ DO** を定義する各インターフェイスを使用するには、少なくとも 1 つの API を提供 (パラメーターまたはプロパティとして、インターフェイス メソッドは、インターフェイスとして型指定された)。</span><span class="sxs-lookup"><span data-stu-id="c6268-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="c6268-117">インターフェイスのデザインを検証するには、この支援を行っています。</span><span class="sxs-lookup"><span data-stu-id="c6268-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="c6268-118">たとえば、<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>消費、<xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c6268-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="c6268-119">**X DO NOT** 以前に出荷されたインターフェイスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6268-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="c6268-120">そうと、インターフェイスの実装ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6268-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="c6268-121">バージョン管理の問題を回避するために、新しいインターフェイスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6268-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="c6268-122">除くこれらのガイドライン」に説明されている場合、マネージ コードの再利用可能なライブラリのデザインのインターフェイスではなく、クラスを選択してください、一般に。</span><span class="sxs-lookup"><span data-stu-id="c6268-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="c6268-123">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="c6268-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c6268-124">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="c6268-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6268-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6268-125">See also</span></span>

- [<span data-ttu-id="c6268-126">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c6268-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="c6268-127">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c6268-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
