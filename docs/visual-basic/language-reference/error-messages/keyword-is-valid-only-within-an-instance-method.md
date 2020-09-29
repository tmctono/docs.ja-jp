---
title: "'<keyword>' は、インスタンス メソッド内でのみ有効です。"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873897"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<keyword>' は、インスタンス メソッド内でのみ有効です。

`Me`、`MyClass`、および `MyBase` キーワードは、特定のクラス インスタンスを参照します。 それらを共有の `Function` または `Sub` プロシージャ内で使用することはできません。  
  
 **エラー ID:** BC30043  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- プロシージャからキーワードを削除するか、プロシージャ宣言から `Shared` キーワードを削除します。  
  
## <a name="see-also"></a>関連項目

- [オブジェクト変数の代入](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me、My、MyBase、および MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [継承の基本](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
