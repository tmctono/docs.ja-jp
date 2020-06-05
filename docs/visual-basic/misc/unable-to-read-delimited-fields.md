---
title: EscapeQuotes が True に設定されている場合、二重引用符は有効な区切り記号でないため、区切り記号で分けられたフィールドを読み取れません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: cd2dd4226296ecd210a1e72a7b7fb593874b0008
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398475"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="90da9-102">EscapeQuotes が True に設定されている場合、二重引用符は有効な区切り記号でないため、区切り記号で分けられたフィールドを読み取れません</span><span class="sxs-lookup"><span data-stu-id="90da9-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="90da9-103">引用符 (") が区切り文字として指定されており、 `TextFieldParser` が `EscapeQuotes` に設定されているため、 `True`はファイルからの読み取りができません。</span><span class="sxs-lookup"><span data-stu-id="90da9-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90da9-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="90da9-104">To correct this error</span></span>  
  
- <span data-ttu-id="90da9-105">`EscapeQuotes` を `False` に設定します。</span><span class="sxs-lookup"><span data-stu-id="90da9-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90da9-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="90da9-106">See also</span></span>

- [<span data-ttu-id="90da9-107">TextFieldParser.SetDelimiters メソッド</span><span class="sxs-lookup"><span data-stu-id="90da9-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="90da9-108">TextFieldParser.Delimiters プロパティ</span><span class="sxs-lookup"><span data-stu-id="90da9-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="90da9-109">方法: コンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="90da9-109">How to: Read From Comma-Delimited Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="90da9-110">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="90da9-110">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
