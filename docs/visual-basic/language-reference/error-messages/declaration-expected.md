---
title: 宣言が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: ee8f1f9ec26dc6c938f0b412dfe30832e3cfe165
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874520"
---
# <a name="declaration-expected"></a>宣言が必要です。

代入ステートメントやループ ステートメントなどの非宣言ステートメントが、プロシージャの外側に記述されています。 プロシージャの外側で許可されるのは宣言のみです。  
  
 または、プログラミング要素が、`Dim` や `Const` などの宣言キーワードを使用せずに宣言されています。  
  
 **エラー ID:** BC30188  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 非宣言ステートメントをプロシージャの本体に移動します。  
  
- 適切な宣言キーワードを使用して、宣言を開始します。  
  
- 宣言キーワードのスペルが間違っていないことを確認します。  
  
## <a name="see-also"></a>関連項目

- [手順](../../programming-guide/language-features/procedures/index.md)
- [Dim ステートメント](../statements/dim-statement.md)
