---
title: "'Class' ステートメントの終わりには、対応する 'End Class' を指定しなければなりません。"
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874613"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>'Class' ステートメントの終わりには、対応する 'End Class' を指定しなければなりません。

`Class` は `Class` ブロックを開始するために使用します。ブロックの先頭にのみ指定でき、対応する`End Class` ステートメントでブロックを終えます。 `Class` ステートメントが重複しているか、`Class` ブロックの最後に `End Class` が使用されませんでした。  
  
 **エラー ID:** BC30481  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 不要な `Class` ステートメントを見つけて削除します。  
  
- 一致する `End Class` で `Class` ブロックを終了します。  
  
## <a name="see-also"></a>関連項目

- [End \<keyword> ステートメント](../statements/end-keyword-statement.md)
- [Class ステートメント](../statements/class-statement.md)
