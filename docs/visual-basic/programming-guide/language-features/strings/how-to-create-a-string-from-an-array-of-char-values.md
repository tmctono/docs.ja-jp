---
title: '方法: Char 値の配列から文字列を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346770"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="63cd7-102">方法: 方法: char 値の配列から文字列を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63cd7-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="63cd7-103">この例では、個々の文字から文字列 "abcd" を作成します。</span><span class="sxs-lookup"><span data-stu-id="63cd7-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63cd7-104">例</span><span class="sxs-lookup"><span data-stu-id="63cd7-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="63cd7-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="63cd7-105">Compile the code</span></span>  
 <span data-ttu-id="63cd7-106">このメソッドには特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="63cd7-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="63cd7-107">引用符で囲まれた単一の文字の後に単一の `c` が続く構文 `"a"c` を使用して、文字リテラルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="63cd7-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="63cd7-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="63cd7-108">Robust Programming</span></span>  
 <span data-ttu-id="63cd7-109">文字列に null 文字 (`Chr(0)` に相当) が含まれていると、文字列を使用したときに予期しない結果が生じます。</span><span class="sxs-lookup"><span data-stu-id="63cd7-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="63cd7-110">文字列に nulll 文字を含めることはできますが、状況によっては、nulll 文字に続く文字が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="63cd7-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63cd7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="63cd7-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="63cd7-112">Char データ型</span><span class="sxs-lookup"><span data-stu-id="63cd7-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="63cd7-113">データの種類</span><span class="sxs-lookup"><span data-stu-id="63cd7-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
