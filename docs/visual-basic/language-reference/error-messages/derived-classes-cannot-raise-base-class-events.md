---
title: 派生クラスで基本クラスのイベントを発生させることはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835142"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="04651-102">派生クラスで基本クラスのイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="04651-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="04651-103">宣言されている宣言領域からのみイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="04651-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="04651-104">そのため、クラスは、その他のクラスを派生元であるものも含めてからイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="04651-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="04651-105">**エラー ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="04651-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04651-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="04651-106">To correct this error</span></span>  
  
-   <span data-ttu-id="04651-107">移動、`Event`ステートメントまたは`RaiseEvent`ステートメント、同じクラスにされるためです。</span><span class="sxs-lookup"><span data-stu-id="04651-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04651-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="04651-108">See also</span></span>

- [<span data-ttu-id="04651-109">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="04651-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="04651-110">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="04651-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
