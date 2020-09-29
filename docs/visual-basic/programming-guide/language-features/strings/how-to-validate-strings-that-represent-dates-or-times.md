---
title: '方法: 日付または時刻を表す文字列を検証する'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f3654894e274404410179dab04422e20f6040440
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072601"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>方法: 日付または時刻を表す文字列を検証する (Visual Basic)

次のコード例では、文字列が有効な日付または時刻を表しているかどうかを示す `Boolean` 値を設定します。  
  
## <a name="example"></a>例  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>コードのコンパイル  

 `("01/01/03")` と `"9:30 PM"` を、検証する日付と時刻に置き換えます。 文字列は、ハードコーディングされた別の文字列、`String` 変数、または文字列を返すメソッド (`InputBox` など) に置き換えることができます。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  

 `String` から `DateTime` 変数への変換を試みる前に、このメソッドを使用して文字列を検証します。 日付または時刻を最初にチェックしておくことで、実行時に例外が生成されないようにすることができます。  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Visual Basic における文字列の検証](validating-strings.md)
