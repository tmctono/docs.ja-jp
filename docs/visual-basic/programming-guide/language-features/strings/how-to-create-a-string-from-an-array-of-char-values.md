---
title: '方法: Char 値 (Visual Basic) の配列から文字列を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054056"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="cd9eb-102">方法: Char 値 (Visual Basic) の配列から文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="cd9eb-103">この例では、個々 の文字から文字列"abcd"を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd9eb-104">例</span><span class="sxs-lookup"><span data-stu-id="cd9eb-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd9eb-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cd9eb-105">Compiling the Code</span></span>  
 <span data-ttu-id="cd9eb-106">このメソッドには、特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="cd9eb-107">構文`"a"c`がある場合、1 つ、`c`引用符内の 1 文字に依存して、文字リテラルを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cd9eb-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="cd9eb-108">Robust Programming</span></span>  
 <span data-ttu-id="cd9eb-109">Null 文字 (に相当`Chr(0)`) 文字列の結果が発生する予期しない文字列を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="cd9eb-110">Null 文字は文字列で含まれますが、状況によっては、null 文字に続く文字は表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9eb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd9eb-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="cd9eb-112">Char データ型</span><span class="sxs-lookup"><span data-stu-id="cd9eb-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="cd9eb-113">データの種類</span><span class="sxs-lookup"><span data-stu-id="cd9eb-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
