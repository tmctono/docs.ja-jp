---
title: "'ReDim' で次元数を変更することはできません"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077372"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' で次元数を変更することはできません

`ReDim` ステートメントを使用して、配列のランク (次元の数) を変更する操作が行われました。 `ReDim` は既に宣言された配列の 1 つ以上の次元のサイズを変更するために使用できますが、配列のランクを変更することはできません。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 次元のサイズではなく、配列のランクを変更しようとしていることを確認します。可能な場合は、 `Dim` を使用して、希望のランクを持つ配列を新規に宣言します。  
  
## <a name="see-also"></a>こちらもご覧ください

- [Visual Basic における配列](../programming-guide/language-features/arrays/index.md)
- [Visual Basic 内の配列の次元](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim ステートメント](../language-reference/statements/redim-statement.md)
- [Dim ステートメント](../language-reference/statements/dim-statement.md)
