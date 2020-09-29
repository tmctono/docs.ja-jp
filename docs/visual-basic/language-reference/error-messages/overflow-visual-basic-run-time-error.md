---
title: オーバーフローしました。(Visual Basic ランタイム エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871217"
---
# <a name="overflow-visual-basic-run-time-error"></a>オーバーフローしました。(Visual Basic ランタイム エラー)

代入の対象の制限を超える代入を試みると、オーバーフローが発生します。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. 代入、計算、およびデータ型の変換の結果が、その型の値に対して許可されている変数の範囲内で表すには大きすぎないことを確認し、必要に応じて、より大きな値の範囲を保持できる型の変数に値を代入します。  
  
2. プロパティへの代入が、代入先のプロパティの範囲に適合することを確認します。  
  
3. 整数に強制的に変換される計算で使用される数値に、整数よりも大きな結果がないことを確認します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [データの種類](../data-types/index.md)
- [エラーの種類](../../programming-guide/language-features/error-types.md)
