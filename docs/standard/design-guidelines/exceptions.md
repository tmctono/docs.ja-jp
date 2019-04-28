---
title: 例外のデザインのガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: KrzysztofCwalina
ms.openlocfilehash: 60c3d25138c224f5eabf44d06b6c9a8373eb5f96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669055"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="c15f2-102">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c15f2-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="c15f2-103">例外処理には戻り値ベースのエラー報告に対する多くの利点です。</span><span class="sxs-lookup"><span data-stu-id="c15f2-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="c15f2-104">適切なフレームワークの設計では、例外の利点を活用するアプリケーション開発者は役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c15f2-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="c15f2-105">このセクションでは、例外の利点を説明し、それらを効果的に使用のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="c15f2-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c15f2-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c15f2-106">In This Section</span></span>  
 [<span data-ttu-id="c15f2-107">例外のスロー</span><span class="sxs-lookup"><span data-stu-id="c15f2-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="c15f2-108">標準例外型の使用</span><span class="sxs-lookup"><span data-stu-id="c15f2-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="c15f2-109">例外とパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c15f2-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="c15f2-110">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="c15f2-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c15f2-111">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="c15f2-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15f2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c15f2-112">See also</span></span>

- [<span data-ttu-id="c15f2-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c15f2-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
