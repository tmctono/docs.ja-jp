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
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785555"
---
# <a name="abstract-class-design"></a><span data-ttu-id="16cb7-102">抽象クラスのデザイン</span><span class="sxs-lookup"><span data-stu-id="16cb7-102">Abstract Class Design</span></span>
<span data-ttu-id="16cb7-103">**X** 抽象型に public または protected のコンストラクターを\*\*定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="16cb7-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="16cb7-104">コンストラクターは、ユーザーがその型のインスタンスを作成する必要がないならば public であるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="16cb7-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="16cb7-105">抽象型のインスタンスを作成することはできないので、public なコンストラクターを持つ抽象型は設計が間違っており、ユーザーに誤解を招きます。</span><span class="sxs-lookup"><span data-stu-id="16cb7-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="16cb7-106">**✓** 抽象クラスには、protected または internal のコンストラクターを\*\*定義してください。</span><span class="sxs-lookup"><span data-stu-id="16cb7-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="16cb7-107">protected コンストラクターはより一般的で、派生型が作成された時に基底クラスが独自の初期化を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16cb7-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="16cb7-108">internal コンストラクターは、その具象実装をアセンブリ内部に制限するために用いることができます。</span><span class="sxs-lookup"><span data-stu-id="16cb7-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="16cb7-109">**✓** 出荷する抽象クラスから継承する具象型を少なくとも 1 つ\*\*提供してください。</span><span class="sxs-lookup"><span data-stu-id="16cb7-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="16cb7-110">こうすることにより、抽象クラスのデザインを検証できます。</span><span class="sxs-lookup"><span data-stu-id="16cb7-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="16cb7-111">たとえば、<xref:System.IO.FileStream?displayProperty=nameWithType>は<xref:System.IO.Stream?displayProperty=nameWithType>の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="16cb7-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="16cb7-112">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="16cb7-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="16cb7-113">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="16cb7-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16cb7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="16cb7-114">See also</span></span>

- [<span data-ttu-id="16cb7-115">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16cb7-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="16cb7-116">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16cb7-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
