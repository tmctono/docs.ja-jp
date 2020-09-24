---
title: 最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 4fb40e5f2b458fbbd0bfdb329f75250e70fd7e28
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083918"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません

最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません。 最後の要素内の 0 以下のフィールド幅は、最後のフィールドが可変長であることを示しています。  
  
 最後の要素以外のフィールド幅が 0 以下に設定されているため、処理に失敗しました。 0 以下のフィールド幅を最後の要素として使用し、最後のフィールドが可変長であることを示すことができますが、他の要素として使用することはできません。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- フィールド幅を正しい長さに設定します。  
  
## <a name="see-also"></a>こちらもご覧ください

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [方法: 固定幅のテキスト ファイルを読み取る](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
