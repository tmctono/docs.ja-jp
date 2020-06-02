---
title: 共通デザイン パターン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
ms.openlocfilehash: 9b9525a7597f7df6c9a554b51160a99f0e06232c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290968"
---
# <a name="common-design-patterns"></a><span data-ttu-id="2565c-102">共通デザイン パターン</span><span class="sxs-lookup"><span data-stu-id="2565c-102">Common Design Patterns</span></span>
<span data-ttu-id="2565c-103">多くの書籍には、ソフトウェアパターン、パターン言語、およびパターンに関する非常に広範なパターンに対応するアンチパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="2565c-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="2565c-104">したがって、この章では、.NET Framework Api の設計で頻繁に使用されるごく限られたパターンセットに関連するガイドラインと説明を示します。</span><span class="sxs-lookup"><span data-stu-id="2565c-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2565c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2565c-105">In This Section</span></span>  
 [<span data-ttu-id="2565c-106">依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="2565c-106">Dependency Properties</span></span>](dependency-properties.md)  
 [<span data-ttu-id="2565c-107">Dispose パターン</span><span class="sxs-lookup"><span data-stu-id="2565c-107">Dispose Pattern</span></span>](../garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="2565c-108">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="2565c-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2565c-109">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="2565c-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2565c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2565c-110">See also</span></span>

- [<span data-ttu-id="2565c-111">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2565c-111">Framework Design Guidelines</span></span>](index.md)
