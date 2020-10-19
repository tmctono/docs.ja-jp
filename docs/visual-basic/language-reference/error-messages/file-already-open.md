---
title: ファイルは既に開かれています。
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162753"
---
# <a name="file-already-open"></a>ファイルは既に開かれています。

別の `FileOpen` またはその他の操作を実行する前に、ファイルを閉じる必要がある場合があります。 このエラーでは以下の原因が考えられます。

- 既に開いているファイルに対して順次出力モードの `FileOpen` 操作が実行されました

- ステートメントが開いているファイルを参照しています。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- ステートメントを実行する前に、ファイルを閉じます。

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
