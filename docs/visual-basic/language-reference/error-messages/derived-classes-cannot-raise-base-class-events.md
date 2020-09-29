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
# <a name="derived-classes-cannot-raise-base-class-events"></a>派生クラスで基本クラスのイベントを発生させることはできません。

イベントを発生させることができるのは、それが宣言されている宣言領域からのみです。 そのため、クラスは、派生元のクラスであっても、他のクラスからイベントを発生させることはできません。  
  
 **エラー ID:** BC30029  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- `Event` ステートメントまたは `RaiseEvent` ステートメントが同じクラス内になるように移動します。  
  
## <a name="see-also"></a>関連項目

- [Event ステートメント](../statements/event-statement.md)
- [RaiseEvent ステートメント](../statements/raiseevent-statement.md)
