---
title: '方法 : 文字列を文字の配列に変換する'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352446"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="922d8-102">方法 : Visual Basic で文字列を文字の配列に変換する</span><span class="sxs-lookup"><span data-stu-id="922d8-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="922d8-103">文字列内の文字に関するデータと文字列内の文字の位置 (文字列を解析する場合など) を使用すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="922d8-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="922d8-104">この例では、文字列の <xref:System.String.ToCharArray%2A> メソッドを呼び出して、文字列内の文字の配列を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="922d8-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="922d8-105">例</span><span class="sxs-lookup"><span data-stu-id="922d8-105">Example</span></span>  
 <span data-ttu-id="922d8-106">この例では、文字列を `Char` 配列に分割する方法と、文字列を Unicode テキスト文字の `String` 配列に分割する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="922d8-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="922d8-107">この区別の理由は、Unicode テキスト文字が2つ以上の `Char` 文字 (サロゲートペアや結合文字シーケンスなど) で構成できることです。</span><span class="sxs-lookup"><span data-stu-id="922d8-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="922d8-108">詳細については、「<xref:System.Globalization.TextElementEnumerator>」および「 [Unicode 標準](https://www.unicode.org/standard/standard.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="922d8-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="922d8-109">例</span><span class="sxs-lookup"><span data-stu-id="922d8-109">Example</span></span>  
 <span data-ttu-id="922d8-110">文字列を Unicode テキスト文字に分割するのはより困難ですが、これは文字列の視覚的表現に関する情報が必要な場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="922d8-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="922d8-111">この例では、<xref:System.Globalization.StringInfo.SubstringByTextElements%2A> メソッドを使用して、文字列を構成する Unicode テキスト文字に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="922d8-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="922d8-112">参照</span><span class="sxs-lookup"><span data-stu-id="922d8-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="922d8-113">方法 : 文字列の文字にアクセスする</span><span class="sxs-lookup"><span data-stu-id="922d8-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="922d8-114">Visual Basic で、文字列型とその他のデータ型との変換を行う</span><span class="sxs-lookup"><span data-stu-id="922d8-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="922d8-115">文字列</span><span class="sxs-lookup"><span data-stu-id="922d8-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
