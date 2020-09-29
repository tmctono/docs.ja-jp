---
title: ステートメントの終わりを指定してください。
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 9141400afc651629df381e0a655e2d7b9da2e45d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874421"
---
# <a name="end-of-statement-expected"></a>ステートメントの終わりを指定してください。

ステートメントは構文的に完全ですが、ステートメントを完了する要素の後に追加のプログラミング要素が続いています。 すべてのステートメントの末尾には、行終端記号が必要です。
  
 行終端記号は、Visual Basic のソース ファイルの文字を行に分割します。 行終端記号の例としては、Unicode 復帰文字 (&HD)、Unicode 改行文字 (&HA)、および Unicode 復帰文字とその後の Unicode 改行文字があります。 行終端記号の詳細については、[Visual Basic 言語の仕様](~/_vblang/spec/lexical-grammar.md#line-terminators)に関するページを参照してください。
  
 **エラー ID:** BC30205
  
## <a name="to-correct-this-error"></a>このエラーを解決するには
  
1. 2 つの異なるステートメントが誤って同じ行に配置されていないかを確認します。
  
2. 行終端記号を、ステートメントを完了する要素の後に挿入します。
  
## <a name="see-also"></a>関連項目

- [方法: コード内でステートメントを分割および連結する](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [ステートメント](../../programming-guide/language-features/statements.md)
