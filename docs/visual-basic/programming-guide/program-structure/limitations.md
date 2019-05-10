---
title: Visual Basic の制限事項
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 9fa0844f4508906ae30b936e41fb4392b74d1437
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648732"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="edb29-102">Visual Basic の制限事項</span><span class="sxs-lookup"><span data-stu-id="edb29-102">Visual Basic Limitations</span></span>
<span data-ttu-id="edb29-103">以前のバージョンの Visual Basic では、変数名、モジュール、およびモジュールのサイズで許可されている変数の数の長さなど、コード内の境界を適用します。</span><span class="sxs-lookup"><span data-stu-id="edb29-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="edb29-104">Visual Basic .net では、これらの制限が緩和されました、書き込みと、コードを配置をより自由を与えます。</span><span class="sxs-lookup"><span data-stu-id="edb29-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="edb29-105">物理的な制限は、実行時メモリよりもよりするコンパイル時の考慮事項に依存します。</span><span class="sxs-lookup"><span data-stu-id="edb29-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="edb29-106">お勧めのプログラミング手法を使用して大規模なアプリケーションを複数のクラスとモジュールに分割する場合は、内部の Visual Basic の制限が発生する可能性はほとんど。</span><span class="sxs-lookup"><span data-stu-id="edb29-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="edb29-107">次に、極端なケースで発生する可能性のあるいくつかの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="edb29-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="edb29-108">**名の長さ。**</span><span class="sxs-lookup"><span data-stu-id="edb29-108">**Name Length.**</span></span> <span data-ttu-id="edb29-109">すべての宣言されたプログラミング要素の名前の文字の最大数です。</span><span class="sxs-lookup"><span data-stu-id="edb29-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="edb29-110">この最大値は、要素名が修飾されている場合に、全体の修飾文字列に適用されます。</span><span class="sxs-lookup"><span data-stu-id="edb29-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="edb29-111">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb29-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="edb29-112">**行の長さ。**</span><span class="sxs-lookup"><span data-stu-id="edb29-112">**Line Length.**</span></span> <span data-ttu-id="edb29-113">最大 65535 文字でソース コードの物理的な行があります。</span><span class="sxs-lookup"><span data-stu-id="edb29-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="edb29-114">論理ソース コード行は行継続文字を使用する場合は、長くすることはできます。</span><span class="sxs-lookup"><span data-stu-id="edb29-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="edb29-115">「[方法:分割および連結コード内でステートメント](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="edb29-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="edb29-116">**配列の次元。**</span><span class="sxs-lookup"><span data-stu-id="edb29-116">**Array Dimensions.**</span></span> <span data-ttu-id="edb29-117">これは、配列に対して宣言できるディメンションの最大数です。</span><span class="sxs-lookup"><span data-stu-id="edb29-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="edb29-118">これにより、インデックスの配列要素を指定する際の数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="edb29-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="edb29-119">参照してください[Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="edb29-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="edb29-120">**文字列の長さ。**</span><span class="sxs-lookup"><span data-stu-id="edb29-120">**String Length.**</span></span> <span data-ttu-id="edb29-121">これは、1 つの文字列に格納できる Unicode 文字の最大数です。</span><span class="sxs-lookup"><span data-stu-id="edb29-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="edb29-122">参照してください[文字列データ型](../../../visual-basic/language-reference/data-types/string-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="edb29-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="edb29-123">**環境文字列の長さ。**</span><span class="sxs-lookup"><span data-stu-id="edb29-123">**Environment String Length.**</span></span> <span data-ttu-id="edb29-124">コマンドライン引数として使用される任意の環境文字列の 32768 文字の最大値があります。</span><span class="sxs-lookup"><span data-stu-id="edb29-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="edb29-125">これは、すべてのプラットフォームでの制限です。</span><span class="sxs-lookup"><span data-stu-id="edb29-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb29-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="edb29-126">See also</span></span>

- [<span data-ttu-id="edb29-127">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="edb29-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="edb29-128">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="edb29-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
