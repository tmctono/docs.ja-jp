---
title: 二重引用符は、EscapeQuote が True に設定されている区切り符号で分けられたフィールドには有効なコメント トークンではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: a66d43d249a12ffa552073866f2e0a1e6d453608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409941"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a><span data-ttu-id="e032e-102">二重引用符は、EscapeQuote が True に設定されている区切り符号で分けられたフィールドには有効なコメント トークンではありません。</span><span class="sxs-lookup"><span data-stu-id="e032e-102">A double quote is not a valid comment token for delimited fields where EscapeQuote is set to True</span></span>

<span data-ttu-id="e032e-103">`TextFieldParser`の区切り記号として二重引用符が指定されましたが、 `EscapeQuotes` に `True`が設定されています。</span><span class="sxs-lookup"><span data-stu-id="e032e-103">A quotation mark has been supplied as the delimiter for the `TextFieldParser`, but `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e032e-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e032e-104">To correct this error</span></span>  
  
- <span data-ttu-id="e032e-105">`EscapeQuotes` を `False` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e032e-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e032e-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="e032e-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [<span data-ttu-id="e032e-107">方法: コンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="e032e-107">How to: Read From Comma-Delimited Text Files</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
