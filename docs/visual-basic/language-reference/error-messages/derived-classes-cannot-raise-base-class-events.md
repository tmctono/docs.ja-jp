---
title: 派生クラスで基本クラスのイベントを発生させることはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874479"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="bc654-102">派生クラスで基本クラスのイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc654-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="bc654-103">イベントを発生させることができるのは、それが宣言されている宣言領域からのみです。</span><span class="sxs-lookup"><span data-stu-id="bc654-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="bc654-104">そのため、クラスは、派生元のクラスであっても、他のクラスからイベントを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc654-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="bc654-105">**エラー ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="bc654-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bc654-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bc654-106">To correct this error</span></span>  
  
- <span data-ttu-id="bc654-107">`Event` ステートメントまたは `RaiseEvent` ステートメントが同じクラス内になるように移動します。</span><span class="sxs-lookup"><span data-stu-id="bc654-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc654-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc654-108">See also</span></span>

- [<span data-ttu-id="bc654-109">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="bc654-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="bc654-110">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="bc654-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
