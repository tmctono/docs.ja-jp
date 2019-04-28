---
title: 行<number>現在の Fieldwidth を使用して解析できません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_MalFormedFixedWidthLine
ms.assetid: 84e14245-dfdf-4b62-8b84-e83a31608899
ms.openlocfilehash: f3184f023ab4663d5616e3878420e3a75a7f3cde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922383"
---
# <a name="line-number-cannot-be-parsed-using-the-current-fieldwidths"></a><span data-ttu-id="28fe6-102">行\<数 > 現在の Fieldwidth を使用して解析できません</span><span class="sxs-lookup"><span data-stu-id="28fe6-102">Line \<number> cannot be parsed using the current FieldWidths</span></span>
<span data-ttu-id="28fe6-103">指定された行のフィールドの幅が指定よりも大きいため、その行を解析できません。</span><span class="sxs-lookup"><span data-stu-id="28fe6-103">The specified line cannot be parsed because its fields have widths other than those specified.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="28fe6-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="28fe6-104">To correct this error</span></span>  
  
- <span data-ttu-id="28fe6-105">行が正しく解析できるように `FieldWidths` を調整するか、またはその行を処理するために例外処理コードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="28fe6-105">Adjust `FieldWidths` so the line can be parsed correctly, or insert exception-handling code in order to handle the line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28fe6-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="28fe6-106">See also</span></span>

- [<span data-ttu-id="28fe6-107">方法: 複数の書式を持つテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="28fe6-107">How to: Read From Text Files with Multiple Formats</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="28fe6-108">My.Computer.FileSystem.OpenTextFieldParser</span><span class="sxs-lookup"><span data-stu-id="28fe6-108">My.Computer.FileSystem.OpenTextFieldParser</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A)
- [<span data-ttu-id="28fe6-109">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="28fe6-109">Parsing Text Files with the TextFieldParser Object</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="28fe6-110">TextFieldParser オブジェクト</span><span class="sxs-lookup"><span data-stu-id="28fe6-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
- [<span data-ttu-id="28fe6-111">TextFieldParser.FieldWidths プロパティ</span><span class="sxs-lookup"><span data-stu-id="28fe6-111">TextFieldParser.FieldWidths Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A)
- [<span data-ttu-id="28fe6-112">TextFieldParser.SetFieldWidths メソッド</span><span class="sxs-lookup"><span data-stu-id="28fe6-112">TextFieldParser.SetFieldWidths Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A)
