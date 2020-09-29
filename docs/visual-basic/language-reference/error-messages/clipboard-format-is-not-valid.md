---
title: クリップボードの形式が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874591"
---
# <a name="clipboard-format-is-not-valid"></a>クリップボードの形式が有効ではありません。

指定されたクリップボードの形式が、実行されるメソッドと互換性がありません。 このエラーでは以下の原因が考えられます。  
  
- クリップボードの `GetText` または `SetText` メソッドに `vbCFText` または `vbCFLink` 以外のクリップボードの形式を使用している。  
  
- クリップボードの `GetData` または `SetData` メソッドに `vbCFBitmap`、`vbCFDIB`、または `vbCFMetafile` 以外のクリップボードの形式を使用している。  
  
- クリップボードの形式が Microsoft Windows に登録されていないときに、登録されている形式 (&HC000-& HFFFF) に対して Microsoft Windows によって予約されている範囲内のクリップボードの形式を使用して、`DataObject` の `GetData` または `SetData` メソッドを使用している。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 無効な形式を削除して、有効な形式を指定してください。  
  
## <a name="see-also"></a>関連項目

- [クリップボード: その他の形式の追加](/cpp/mfc/clipboard-adding-other-formats)
