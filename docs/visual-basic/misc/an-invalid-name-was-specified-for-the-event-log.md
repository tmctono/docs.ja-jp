---
title: イベント ログに無効な名前が指定されました
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 36e2bc91a671a22e808d0e30e292471729b1e50b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083879"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>イベント ログに無効な名前が指定されました

イベント ログに無効な名前が指定されました。 通常これは、名前に含まれる無効な文字、空のファイル名、または長すぎるファイル名の結果です。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 指定した名前が 8 文字を超える場合、他のイベント ログの名前と競合しないことを確認します。 名前が一意であるかどうかを判断するときには、最初の 8 文字のみが評価されます。  
  
- パスを指定する場合は、正しく解析されることを確認します。  
  
- 名前に無効な文字がないことを確認してください。 ファイル名に使用できない文字には `<`、 `>`、 `:`、 `"`、 `/`、 `\`、および `|`があります。  
  
## <a name="see-also"></a>こちらもご覧ください

- [方法: ファイル パスを解析する](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [方法: ファイルの名前を変更する](../developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
