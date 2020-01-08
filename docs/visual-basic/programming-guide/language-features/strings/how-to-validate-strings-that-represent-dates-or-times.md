---
title: '方法: 日付または時刻を表す文字列を検証する'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348411"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="cc555-102">方法: 日付または時刻を表す文字列を検証する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc555-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="cc555-103">次のコード例では、文字列が有効な日付または時刻を表すかどうかを示す `Boolean` 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="cc555-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc555-104">使用例</span><span class="sxs-lookup"><span data-stu-id="cc555-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="cc555-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cc555-105">Compile the code</span></span>  
 <span data-ttu-id="cc555-106">`("01/01/03")` と `"9:30 PM"` を、検証する日付と時刻に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cc555-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="cc555-107">文字列を別のハードコーディングされた文字列に置き換えたり、`String` 変数を使用したり、文字列を返すメソッド (`InputBox`など) に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="cc555-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cc555-108">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="cc555-108">Robust Programming</span></span>  
 <span data-ttu-id="cc555-109">`String` を `DateTime` 変数に変換する前に、このメソッドを使用して文字列を検証します。</span><span class="sxs-lookup"><span data-stu-id="cc555-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="cc555-110">最初に日付または時刻を確認することで、実行時に例外が生成されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc555-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc555-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc555-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="cc555-112">Visual Basic における文字列の検証</span><span class="sxs-lookup"><span data-stu-id="cc555-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
