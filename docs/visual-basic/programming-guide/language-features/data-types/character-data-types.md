---
title: 文字データ型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965677"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="a6744-102">文字データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6744-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="a6744-103">Visual Basic には、印刷可能な文字と表示可能な文字を処理する*文字データ型*が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6744-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="a6744-104">どちらも Unicode 文字を処理します`Char`が、は1つ`String`の文字を保持しますが、には無限の文字数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6744-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="a6744-105">Visual Basic のデータ型の並列比較を表示するテーブルについては、「[データ型](../../../../visual-basic/language-reference/data-types/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6744-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="a6744-106">Char 型</span><span class="sxs-lookup"><span data-stu-id="a6744-106">Char Type</span></span>  
 <span data-ttu-id="a6744-107">`Char`データ型は、1つの2バイト (16 ビット) Unicode 文字です。</span><span class="sxs-lookup"><span data-stu-id="a6744-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="a6744-108">変数が常に1つの文字を正確に格納`Char`する場合は、として宣言します。</span><span class="sxs-lookup"><span data-stu-id="a6744-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="a6744-109">例:</span><span class="sxs-lookup"><span data-stu-id="a6744-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="a6744-110">変数`Char`または`String`変数に指定できる値は、Unicode 文字セットの*コードポイント*(文字コード) です。</span><span class="sxs-lookup"><span data-stu-id="a6744-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="a6744-111">Unicode 文字には、基本的な ASCII 文字セット、その他のさまざまなアルファベット文字、アクセント、通貨記号、分数、分音記号、数学、およびテクニカルシンボルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6744-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6744-112">Unicode 文字セットでは、*サロゲートペア*の DFFF (55296 ~ 55551 decimal) を介してコードポイント D800 が予約されています。これには、1つのコードポイントを表す 2 16 ビット値が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6744-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="a6744-113">変数`Char`はサロゲートペアを保持できず、は`String` 2 つの位置を使用してこのペアを保持します。</span><span class="sxs-lookup"><span data-stu-id="a6744-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="a6744-114">詳細については、「 [Char データ型](../../../../visual-basic/language-reference/data-types/char-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6744-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="a6744-115">文字列型</span><span class="sxs-lookup"><span data-stu-id="a6744-115">String Type</span></span>  
 <span data-ttu-id="a6744-116">データ`String`型は、0個以上の2バイト (16 ビット) Unicode 文字のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="a6744-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="a6744-117">変数に不特定数の文字を含めることができる場合は、 `String`として宣言します。</span><span class="sxs-lookup"><span data-stu-id="a6744-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="a6744-118">例:</span><span class="sxs-lookup"><span data-stu-id="a6744-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="a6744-119">詳細については、「 [String データ型](../../../../visual-basic/language-reference/data-types/string-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6744-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6744-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6744-120">See also</span></span>

- [<span data-ttu-id="a6744-121">基本データ型</span><span class="sxs-lookup"><span data-stu-id="a6744-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="a6744-122">複合データ型</span><span class="sxs-lookup"><span data-stu-id="a6744-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a6744-123">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="a6744-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a6744-124">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="a6744-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a6744-125">Visual Basic での型変換</span><span class="sxs-lookup"><span data-stu-id="a6744-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="a6744-126">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="a6744-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a6744-127">型文字</span><span class="sxs-lookup"><span data-stu-id="a6744-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
