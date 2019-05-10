---
title: 最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: c1537133300ac4de33d0d7ebc3ea0ad6768e8ec9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609147"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a><span data-ttu-id="0f310-102">最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません</span><span class="sxs-lookup"><span data-stu-id="0f310-102">All field widths, except the last element, must be greater than zero</span></span>
<span data-ttu-id="0f310-103">最後の要素以外のすべてのフィールド幅は 0 より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0f310-103">All field widths, except the last element, must be greater than zero.</span></span> <span data-ttu-id="0f310-104">最後の要素内の 0 以下のフィールド幅は、最後のフィールドが可変長であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="0f310-104">A field width less than or equal to zero in the last element indicates the last field is of variable length.</span></span>  
  
 <span data-ttu-id="0f310-105">最後の要素以外のフィールド幅が 0 以下に設定されているため、処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0f310-105">The operation has failed because a field width other than the last element is set to zero or less.</span></span> <span data-ttu-id="0f310-106">0 以下のフィールド幅を最後の要素として使用し、最後のフィールドが可変長であることを示すことができますが、他の要素として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f310-106">A field width less than or equal to zero can be used as the last element to indicate that the last field is of variable length, but it cannot be used as any other element.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f310-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0f310-107">To correct this error</span></span>  
  
- <span data-ttu-id="0f310-108">フィールド幅を正しい長さに設定します。</span><span class="sxs-lookup"><span data-stu-id="0f310-108">Set the field width to the correct length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f310-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f310-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [<span data-ttu-id="0f310-110">方法: 固定幅のテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="0f310-110">How to: Read From Fixed-width Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="0f310-111">TextFieldParser オブジェクト</span><span class="sxs-lookup"><span data-stu-id="0f310-111">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
