---
title: 先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873851"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。

`With` ブロック内にないピリオド (.) または感嘆符 (!) が、左側に式がない状態で指定されています。 メンバー アクセス (`.`) とディクショナリ メンバー アクセス (`!`) には、メンバーが含まれている要素を指定した式が必要になります。 これは、アクセサーのすぐ左側、またはメンバー アクセスを含む `With` ブロックのターゲットとして指定されている必要があります。  
  
 **エラー ID:** BC30157  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. `With` ブロックが正しく書式設定されていることを確認します。  
  
2. `With` ブロックがない場合は、アクセサーの左側に、メンバーを含む定義済みの要素に評価される式を追加します。  
  
## <a name="see-also"></a>関連項目

- [コード内の特殊文字](../../programming-guide/program-structure/special-characters-in-code.md)
- [With...End With ステートメント](../statements/with-end-with-statement.md)
