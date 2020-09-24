---
title: 区切り記号は Nothing または空の文字列は使用できません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_DelimiterNothing
ms.assetid: 8885fcd1-c201-409d-9a32-6ff2b13c0c13
ms.openlocfilehash: 786eb2bddc967e9b5b8fd6afec3ffbe264814834
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084932"
---
# <a name="a-delimiter-cannot-be-nothing-or-an-empty-string"></a>区切り記号は Nothing または空の文字列は使用できません

`TextFieldParser` プロパティが `Delimiters` に設定されているか、または空 `Nothing` ("") であるため、 `String` をファイルから読み取ることができません。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- `Delimiters`に対して有効な値を指定します。  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters>
- [方法: コンマ区切りのテキスト ファイルを読み取る](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
- [TextFieldParser オブジェクトによるテキスト ファイルの解析](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
