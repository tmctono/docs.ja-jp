---
title: ファイルは既に開かれています。
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874167"
---
# <a name="file-already-open"></a>ファイルは既に開かれています。

別の `FileOpen` またはその他の操作を実行する前に、ファイルを閉じる必要がある場合があります。 このエラーでは以下の原因が考えられます。  
  
- 既に開いているファイルに対して順次出力モードの `FileOpen` 操作が実行されました  
  
- ステートメントが開いているファイルを参照しています。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. ステートメントを実行する前に、ファイルを閉じます。  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
