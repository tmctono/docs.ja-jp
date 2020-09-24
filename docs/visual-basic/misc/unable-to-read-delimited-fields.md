---
title: EscapeQuotes が True に設定されている場合、二重引用符は有効な区切り記号でないため、区切り記号で分けられたフィールドを読み取れません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 29682edb78b848897ac2999f2d84dc1a9c1a3367
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100359"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="ce8b3-102">EscapeQuotes が True に設定されている場合、二重引用符は有効な区切り記号でないため、区切り記号で分けられたフィールドを読み取れません</span><span class="sxs-lookup"><span data-stu-id="ce8b3-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>

<span data-ttu-id="ce8b3-103">引用符 (") が区切り文字として指定されており、 `TextFieldParser` が `EscapeQuotes` に設定されているため、 `True`はファイルからの読み取りができません。</span><span class="sxs-lookup"><span data-stu-id="ce8b3-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce8b3-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ce8b3-104">To correct this error</span></span>  
  
- <span data-ttu-id="ce8b3-105">`EscapeQuotes` を `False` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ce8b3-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8b3-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce8b3-106">See also</span></span>

- [<span data-ttu-id="ce8b3-107">TextFieldParser.SetDelimiters メソッド</span><span class="sxs-lookup"><span data-stu-id="ce8b3-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="ce8b3-108">TextFieldParser.Delimiters プロパティ</span><span class="sxs-lookup"><span data-stu-id="ce8b3-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="ce8b3-109">方法: コンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="ce8b3-109">How to: Read From Comma-Delimited Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="ce8b3-110">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="ce8b3-110">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
