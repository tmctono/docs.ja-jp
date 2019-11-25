---
title: '方法 : 文字列の文字にアクセスする'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352456"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="4de0b-102">方法 : Visual Basic で文字列の文字にアクセスする</span><span class="sxs-lookup"><span data-stu-id="4de0b-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="4de0b-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span><span class="sxs-lookup"><span data-stu-id="4de0b-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de0b-104">例</span><span class="sxs-lookup"><span data-stu-id="4de0b-104">Example</span></span>  
 <span data-ttu-id="4de0b-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span><span class="sxs-lookup"><span data-stu-id="4de0b-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="4de0b-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span><span class="sxs-lookup"><span data-stu-id="4de0b-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="4de0b-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span><span class="sxs-lookup"><span data-stu-id="4de0b-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4de0b-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="4de0b-108">Robust Programming</span></span>  
 <span data-ttu-id="4de0b-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span><span class="sxs-lookup"><span data-stu-id="4de0b-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="4de0b-110">However, some Unicode characters can be represented by more than one character.</span><span class="sxs-lookup"><span data-stu-id="4de0b-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="4de0b-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="4de0b-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="4de0b-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span><span class="sxs-lookup"><span data-stu-id="4de0b-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de0b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4de0b-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="4de0b-114">方法 : 文字列を文字の配列に変換する</span><span class="sxs-lookup"><span data-stu-id="4de0b-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="4de0b-115">Visual Basic で、文字列型とその他のデータ型との変換を行う</span><span class="sxs-lookup"><span data-stu-id="4de0b-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="4de0b-116">文字列</span><span class="sxs-lookup"><span data-stu-id="4de0b-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
