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
# <a name="a-delimiter-cannot-be-nothing-or-an-empty-string"></a><span data-ttu-id="9a532-102">区切り記号は Nothing または空の文字列は使用できません</span><span class="sxs-lookup"><span data-stu-id="9a532-102">A delimiter cannot be Nothing or an empty String</span></span>

<span data-ttu-id="9a532-103">`TextFieldParser` プロパティが `Delimiters` に設定されているか、または空 `Nothing` ("") であるため、 `String` をファイルから読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="9a532-103">The `TextFieldParser` is unable to read from the file because the `Delimiters` property is set to `Nothing` or is an empty `String` ("").</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a532-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9a532-104">To correct this error</span></span>  
  
- <span data-ttu-id="9a532-105">`Delimiters`に対して有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a532-105">Supply a valid value for `Delimiters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a532-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a532-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters>
- [<span data-ttu-id="9a532-107">方法: コンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="9a532-107">How to: Read From Comma-Delimited Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="9a532-108">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="9a532-108">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
- [<span data-ttu-id="9a532-109">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="9a532-109">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
