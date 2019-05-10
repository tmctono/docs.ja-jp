---
title: 派生クラスで基本クラスのイベントを発生させることはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 030c9c2ffa97572298b23f05c23e3af0df7387b0
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913161"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="51b4c-102">派生クラスで基本クラスのイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="51b4c-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="51b4c-103">宣言されている宣言領域からのみイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="51b4c-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="51b4c-104">そのため、クラスは、その他のクラスを派生元であるものも含めてからイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="51b4c-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="51b4c-105">**エラー ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="51b4c-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51b4c-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="51b4c-106">To correct this error</span></span>  
  
- <span data-ttu-id="51b4c-107">移動、`Event`ステートメントまたは`RaiseEvent`ステートメント、同じクラスにされるためです。</span><span class="sxs-lookup"><span data-stu-id="51b4c-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b4c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="51b4c-108">See also</span></span>

- [<span data-ttu-id="51b4c-109">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="51b4c-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="51b4c-110">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="51b4c-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
