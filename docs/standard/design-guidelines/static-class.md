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
ms.openlocfilehash: 104fa204a95ef31d34e224348068e3a6505aded5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743595"
---
# <a name="static-class-design"></a><span data-ttu-id="cec74-102">静的クラスのデザイン</span><span class="sxs-lookup"><span data-stu-id="cec74-102">Static Class Design</span></span>
<span data-ttu-id="cec74-103">静的クラスは、静的メンバーのみを含むクラスとして定義されます (もちろん、<xref:System.Object?displayProperty=nameWithType> から継承されたインスタンスメンバーと、場合によってはプライベートコンストラクター)。</span><span class="sxs-lookup"><span data-stu-id="cec74-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="cec74-104">一部の言語では、静的クラスのサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cec74-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="cec74-105">2\.0 C#以降では、クラスが静的として宣言されている場合、そのクラスは sealed で abstract であり、インスタンスメンバーをオーバーライドまたは宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="cec74-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="cec74-106">静的クラスは、純粋なオブジェクト指向設計と単純さの間で妥協をします。</span><span class="sxs-lookup"><span data-stu-id="cec74-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="cec74-107">一般的に、他の操作 (<xref:System.IO.File?displayProperty=nameWithType>など)、拡張メソッドの所有者、または完全なオブジェクト指向ラッパーを認められする機能 (<xref:System.Environment?displayProperty=nameWithType>など) へのショートカットを提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cec74-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="cec74-108">✔️静的クラスは控えめに使用してください。</span><span class="sxs-lookup"><span data-stu-id="cec74-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="cec74-109">静的クラスは、フレームワークのオブジェクト指向コアのサポートクラスとしてのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec74-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="cec74-110">静的クラスをその他のバケットとして扱うことは ❌ ません。</span><span class="sxs-lookup"><span data-stu-id="cec74-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="cec74-111">❌ 静的クラスでインスタンスメンバーを宣言またはオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="cec74-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="cec74-112">静的クラスが静的クラスに対して組み込みサポートされていない場合は、静的なクラスをシール、抽象型として宣言し、プライベートインスタンスコンストラクターを追加✔️ます。</span><span class="sxs-lookup"><span data-stu-id="cec74-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="cec74-113">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="cec74-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="cec74-114">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="cec74-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="cec74-115">参照</span><span class="sxs-lookup"><span data-stu-id="cec74-115">See also</span></span>

- [<span data-ttu-id="cec74-116">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cec74-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="cec74-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cec74-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
