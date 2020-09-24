---
title: エンコードは Nothing に設定できません
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 0356098ca3fb41804ea396b0ff792cf2990b3340
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077541"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>エンコードは Nothing に設定できません

パラメーター `encoding` が `Nothing` に設定されていますが、正しい値が必要なため、ファイルへの読み取りまたは書き込みに失敗しました。  
  
 <xref:System.Text.Encoding> は、ファイルへの書き込み時に使用するエンコードを判別するのに使用されます。 既定は UTF-8 です。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 正しい値を `encoding` パラメーターに指定します。  
  
## <a name="see-also"></a>こちらもご覧ください

- [ファイル エンコーディング](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [ファイルの読み取り](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [ファイルへの書き込み](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. System.io.file.readalltext](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. Microsoft.visualbasic.fileio.filesystem.writealltext](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
