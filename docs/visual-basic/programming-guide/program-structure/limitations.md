---
title: 制限事項
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: f7e19977a011565bb4b1536af5cab195f8a01017
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347366"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="9d6dd-102">Visual Basic の制限事項</span><span class="sxs-lookup"><span data-stu-id="9d6dd-102">Visual Basic Limitations</span></span>
<span data-ttu-id="9d6dd-103">以前のバージョンの Visual Basic では、変数名の長さ、モジュールで許容される変数の数、モジュールのサイズなど、コードに境界が適用されていました。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="9d6dd-104">Visual Basic .NET では、これらの制限は緩和されているため、コードの記述と配置をより自由に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="9d6dd-105">物理的な制限は、コンパイル時の考慮事項に比べて、実行時のメモリに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="9d6dd-106">賢明なプログラミングプラクティスを使用し、大規模なアプリケーションを複数のクラスとモジュールに分割する場合、内部的な Visual Basic 制限が発生する可能性はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="9d6dd-107">極端な場合に発生する可能性があるいくつかの制限を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="9d6dd-108">**名前の長さ。**</span><span class="sxs-lookup"><span data-stu-id="9d6dd-108">**Name Length.**</span></span> <span data-ttu-id="9d6dd-109">宣言されたすべてのプログラミング要素の名前には最大文字数があります。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="9d6dd-110">要素名が修飾されている場合、この最大値は修飾文字列全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="9d6dd-111">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="9d6dd-112">**行の長さ。**</span><span class="sxs-lookup"><span data-stu-id="9d6dd-112">**Line Length.**</span></span> <span data-ttu-id="9d6dd-113">ソースコードの物理的な行には、最大65535文字があります。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="9d6dd-114">行連結文字を使用すると、論理ソースコード行が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="9d6dd-115">「[方法: コード内のステートメントを分割して結合する](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="9d6dd-116">**配列の次元。**</span><span class="sxs-lookup"><span data-stu-id="9d6dd-116">**Array Dimensions.**</span></span> <span data-ttu-id="9d6dd-117">配列に対して宣言できる次元の最大数があります。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="9d6dd-118">これにより、配列要素を指定するために使用できるインデックスの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="9d6dd-119">[Visual Basic の配列ディメンションを](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="9d6dd-120">**文字列の長さ。**</span><span class="sxs-lookup"><span data-stu-id="9d6dd-120">**String Length.**</span></span> <span data-ttu-id="9d6dd-121">Unicode 文字の最大数は、1つの文字列に格納できます。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="9d6dd-122">「 [String データ型](../../../visual-basic/language-reference/data-types/string-data-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="9d6dd-123">**環境文字列の長さ。**</span><span class="sxs-lookup"><span data-stu-id="9d6dd-123">**Environment String Length.**</span></span> <span data-ttu-id="9d6dd-124">コマンドライン引数として使用される環境文字列には、最大32768文字があります。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="9d6dd-125">これは、すべてのプラットフォームに関する制限です。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6dd-126">参照</span><span class="sxs-lookup"><span data-stu-id="9d6dd-126">See also</span></span>

- [<span data-ttu-id="9d6dd-127">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="9d6dd-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="9d6dd-128">Visual Basic 名前付け規則</span><span class="sxs-lookup"><span data-stu-id="9d6dd-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
