---
title: リソースに名前を付ける
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709167"
---
# <a name="naming-resources"></a><span data-ttu-id="16ef9-102">リソースに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="16ef9-102">Naming Resources</span></span>
<span data-ttu-id="16ef9-103">ローカライズ可能なリソースは、プロパティのように特定のオブジェクトを介して参照できるので、リソースの名前付けガイドラインはプロパティガイドラインに似ています。</span><span class="sxs-lookup"><span data-stu-id="16ef9-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="16ef9-104">**✓ DO** リソース キーで pascal 表記を使用を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ef9-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="16ef9-105">**✓ DO** 短い識別子ではなくわかりやすいを提供します。</span><span class="sxs-lookup"><span data-stu-id="16ef9-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="16ef9-106">**X DO NOT** メインの CLR 言語の言語固有のキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="16ef9-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="16ef9-107">**✓ DO** のみ英数字とアンダー スコアを使用してリソースの名前付けで使用します。</span><span class="sxs-lookup"><span data-stu-id="16ef9-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="16ef9-108">**✓ DO** 例外メッセージのリソースに対して次の命名規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ef9-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="16ef9-109">リソース識別子は、例外の種類の名前に例外の短い識別子を加えたものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ef9-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="16ef9-110">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="16ef9-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="16ef9-111">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="16ef9-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ef9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="16ef9-112">See also</span></span>

- [<span data-ttu-id="16ef9-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16ef9-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="16ef9-114">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16ef9-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
