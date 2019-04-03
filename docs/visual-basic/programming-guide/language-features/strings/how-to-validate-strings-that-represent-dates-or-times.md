---
title: '方法: 日付または時刻を表す文字列を検証 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f24ff05e48327c21c02eb92b07db17266f743a80
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815231"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="f5cf2-102">方法: 日付または時刻を表す文字列を検証 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5cf2-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="f5cf2-103">次のコード例のセットを`Boolean`文字列が有効な日付または時刻を表すかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="f5cf2-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5cf2-104">例</span><span class="sxs-lookup"><span data-stu-id="f5cf2-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5cf2-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f5cf2-105">Compiling the Code</span></span>  
 <span data-ttu-id="f5cf2-106">置換`("01/01/03")`と`"9:30 PM"`日付と時刻に検証したいとします。</span><span class="sxs-lookup"><span data-stu-id="f5cf2-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="f5cf2-107">文字列を別のハード コーディングされた文字列を置き換えることができます、`String`など、文字列を返す変数、またはメソッドで`InputBox`します。</span><span class="sxs-lookup"><span data-stu-id="f5cf2-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f5cf2-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="f5cf2-108">Robust Programming</span></span>  
 <span data-ttu-id="f5cf2-109">このメソッドに変換する前に、文字列の検証を使用して、`String`を`DateTime`変数。</span><span class="sxs-lookup"><span data-stu-id="f5cf2-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="f5cf2-110">最初の日付または時刻をチェックする場合は、実行時に例外を生成を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f5cf2-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5cf2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5cf2-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="f5cf2-112">Visual Basic における文字列の検証</span><span class="sxs-lookup"><span data-stu-id="f5cf2-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
