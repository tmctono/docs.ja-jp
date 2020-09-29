---
title: メソッドや複数行のラムダの内部では有効でないステートメントです。
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870622"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>メソッドや複数行のラムダの内部では有効でないステートメントです。

ステートメントは、`Sub`、`Function`、プロパティ `Get`、またはプロパティ `Set` プロシージャ内で無効です。 一部のステートメントは、モジュール レベルまたはクラス レベルで配置できます。 `Option Strict` などの他のものは、名前空間レベルで、他のすべての宣言の前に配置する必要があります。  
  
 **エラー ID:** BC30024  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- プロシージャからステートメントを削除します。  
  
## <a name="see-also"></a>関連項目

- [Sub ステートメント](../statements/sub-statement.md)
- [Function ステートメント](../statements/function-statement.md)
- [Get ステートメント](../statements/get-statement.md)
- [Set ステートメント](../statements/set-statement.md)
