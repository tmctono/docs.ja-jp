---
title: 抽象クラスのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709596"
---
# <a name="abstract-class-design"></a><span data-ttu-id="2560b-102">抽象クラスのデザイン</span><span class="sxs-lookup"><span data-stu-id="2560b-102">Abstract Class Design</span></span>
<span data-ttu-id="2560b-103">**X** 抽象型に public または protected のコンストラクターを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="2560b-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="2560b-104">コンストラクターは、ユーザーがその型のインスタンスを作成する必要がないならば public であるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="2560b-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="2560b-105">抽象型のインスタンスを作成することはできないので、public なコンストラクターを持つ抽象型は設計が間違っており、ユーザーに誤解を招きます。</span><span class="sxs-lookup"><span data-stu-id="2560b-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="2560b-106">**✓** 抽象クラスには、protected または internal のコンストラクターを定義してください。</span><span class="sxs-lookup"><span data-stu-id="2560b-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="2560b-107">protected コンストラクターはより一般的で、派生型が作成された時に基底クラスが独自の初期化を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2560b-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="2560b-108">internal コンストラクターは、その具象実装をアセンブリ内部に制限するために用いることができます。</span><span class="sxs-lookup"><span data-stu-id="2560b-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="2560b-109">**✓** 出荷する抽象クラスから継承する具象型を少なくとも 1 つ提供してください。</span><span class="sxs-lookup"><span data-stu-id="2560b-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="2560b-110">こうすることにより、抽象クラスのデザインを検証できます。</span><span class="sxs-lookup"><span data-stu-id="2560b-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="2560b-111">たとえば、<xref:System.IO.FileStream?displayProperty=nameWithType>は<xref:System.IO.Stream?displayProperty=nameWithType>の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="2560b-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="2560b-112">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="2560b-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2560b-113">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="2560b-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2560b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2560b-114">See also</span></span>

- [<span data-ttu-id="2560b-115">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2560b-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="2560b-116">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2560b-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
