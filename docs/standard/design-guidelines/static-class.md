---
title: 静的クラスのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762047"
---
# <a name="static-class-design"></a><span data-ttu-id="462c6-102">静的クラスのデザイン</span><span class="sxs-lookup"><span data-stu-id="462c6-102">Static Class Design</span></span>
<span data-ttu-id="462c6-103">静的クラスは、静的メンバーのみを含んでいるクラスとして定義されます (から継承されたインスタンス メンバーだけでなくもちろん<xref:System.Object?displayProperty=nameWithType>とコンス トラクターはプライベート可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="462c6-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="462c6-104">一部の言語では、静的クラスの組み込みサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="462c6-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="462c6-105">C# 2.0 以降では、クラスが静的に宣言されると、これはシール、抽象クラスで、インスタンス メンバーをオーバーライドまたは宣言されていることができます。</span><span class="sxs-lookup"><span data-stu-id="462c6-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="462c6-106">静的クラスは、純粋なオブジェクト指向設計と単純さのバランスです。</span><span class="sxs-lookup"><span data-stu-id="462c6-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="462c6-107">その他の操作へのショートカットを提供によく使用されます (など<xref:System.IO.File?displayProperty=nameWithType>)、拡張メソッド、または完全なオブジェクト指向ラッパーが保証されているいない機能の保持者 (など<xref:System.Environment?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="462c6-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="462c6-108">**✓ DO** 静的クラスを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="462c6-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="462c6-109">静的クラスは、オブジェクト指向のコア フレームワークのサポート クラスとしてのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462c6-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="462c6-110">**X DO NOT** 静的クラスをその他のバケットとして扱います。</span><span class="sxs-lookup"><span data-stu-id="462c6-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="462c6-111">**X DO NOT** 宣言または静的クラスでインスタンス メンバーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="462c6-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="462c6-112">**✓ DO** として、シールされた抽象クラスで静的クラスを宣言し、使用するプログラミング言語には静的クラスの組み込みサポートがない場合は、プライベート インスタンス コンス トラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="462c6-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="462c6-113">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="462c6-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="462c6-114">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="462c6-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462c6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="462c6-115">See also</span></span>

- [<span data-ttu-id="462c6-116">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="462c6-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="462c6-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="462c6-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
