---
title: 派生クラスで基本クラスのイベントを発生させることはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409700"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="90a5c-102">派生クラスで基本クラスのイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="90a5c-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="90a5c-103">イベントを発生させることができるのは、それが宣言されている宣言領域からのみです。</span><span class="sxs-lookup"><span data-stu-id="90a5c-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="90a5c-104">そのため、クラスは、派生元のクラスであっても、他のクラスからイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="90a5c-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="90a5c-105">**エラー ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="90a5c-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90a5c-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="90a5c-106">To correct this error</span></span>  
  
- <span data-ttu-id="90a5c-107">`Event` ステートメントまたは `RaiseEvent` ステートメントが同じクラス内になるように移動します。</span><span class="sxs-lookup"><span data-stu-id="90a5c-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a5c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="90a5c-108">See also</span></span>

- [<span data-ttu-id="90a5c-109">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="90a5c-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="90a5c-110">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="90a5c-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
