---
title: 文字データ型
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: edd1d3a41dd878649aa422256b7858d7bce366e1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346390"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="1e844-102">文字データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e844-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="1e844-103">Visual Basic には、印刷や表示が可能な文字を処理するための "*文字データ型*" が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1e844-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="1e844-104">どちらも Unicode 文字を処理しますが、`Char` は 1 つの文字を保持するのに対し、`String` は不特定数の文字を含みます。</span><span class="sxs-lookup"><span data-stu-id="1e844-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="1e844-105">Visual Basic データ型を並べて比較している表を、[データ型](../../../../visual-basic/language-reference/data-types/index.md)に関するページで参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e844-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="1e844-106">Char 型</span><span class="sxs-lookup"><span data-stu-id="1e844-106">Char Type</span></span>  
 <span data-ttu-id="1e844-107">`Char` データ型は、1 つの 2 バイト (16 ビット) Unicode 文字です。</span><span class="sxs-lookup"><span data-stu-id="1e844-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="1e844-108">常に変数が厳密に 1 つの文字を格納する場合は、`Char` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="1e844-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="1e844-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1e844-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="1e844-110">`Char` または `String` 変数に含めることができる値は、"*コード ポイント*"、つまり Unicode 文字セットの文字コードです。</span><span class="sxs-lookup"><span data-stu-id="1e844-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="1e844-111">Unicode 文字には、基本的な ASCII 文字セット、その他のさまざまなアルファベット文字、アクセント記号、通貨記号、分数、分音記号、数学記号、および技術用記号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e844-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e844-112">Unicode 文字セットでは、"*サロゲート ペア*" (1 つのコード ポイントを表すために 2 つの 16 ビット値を必要とする) のためにコード ポイント D800 から DFFF (10 進数では 55296 から 55551) が予約されています。</span><span class="sxs-lookup"><span data-stu-id="1e844-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="1e844-113">`Char` 変数はサロゲート ペアを保持できません。`String` は 2 つの位置を使用してこのようなペアを保持します。</span><span class="sxs-lookup"><span data-stu-id="1e844-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="1e844-114">詳細については、「[文字型 (Char)](../../../../visual-basic/language-reference/data-types/char-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e844-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="1e844-115">文字列の種類</span><span class="sxs-lookup"><span data-stu-id="1e844-115">String Type</span></span>  
 <span data-ttu-id="1e844-116">`String` データ型は、0 個以上の 2 バイト (16 ビット) Unicode 文字のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="1e844-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="1e844-117">変数が不特定数の文字を含む可能性がある場合は、`String` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="1e844-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="1e844-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1e844-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="1e844-119">詳細については、「[文字列型 (String)](../../../../visual-basic/language-reference/data-types/string-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e844-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e844-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e844-120">See also</span></span>

- [<span data-ttu-id="1e844-121">基本データ型</span><span class="sxs-lookup"><span data-stu-id="1e844-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="1e844-122">複合データ型</span><span class="sxs-lookup"><span data-stu-id="1e844-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="1e844-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e844-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="1e844-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="1e844-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="1e844-125">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="1e844-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="1e844-126">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="1e844-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="1e844-127">型文字</span><span class="sxs-lookup"><span data-stu-id="1e844-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
