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
ms.openlocfilehash: abe4acd5850aa6065bf4f6fd41bc610ede7ad13f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097957"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="ba0d8-102">Visual Basic の制限事項</span><span class="sxs-lookup"><span data-stu-id="ba0d8-102">Visual Basic Limitations</span></span>

<span data-ttu-id="ba0d8-103">以前のバージョンの Visual Basic では、変数名の長さ、モジュールで許可される変数の数、モジュール サイズなど、コードに上限が適用されていました。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="ba0d8-104">Visual Basic .NET では、これらの制限が緩和され、コードをより自由に記述および配置できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="ba0d8-105">物理的な制限は、コンパイル時の考慮事項よりも実行時のメモリに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="ba0d8-106">慎重なプログラミング プラクティスを使用し、大規模なアプリケーションを複数のクラスやモジュールに分割すれば、Visual Basic の内部的な制限が発生する可能性はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="ba0d8-107">極端な場合に発生する可能性があるいくつかの制限を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="ba0d8-108">**名前の長さ:**</span><span class="sxs-lookup"><span data-stu-id="ba0d8-108">**Name Length.**</span></span> <span data-ttu-id="ba0d8-109">宣言されるすべてのプログラミング要素の名前には最大文字数があります。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="ba0d8-110">要素名が修飾されている場合、この最大数は修飾文字列全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="ba0d8-111">「 [Declared Element Names](../language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-111">See [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="ba0d8-112">**行の長さ:**</span><span class="sxs-lookup"><span data-stu-id="ba0d8-112">**Line Length.**</span></span> <span data-ttu-id="ba0d8-113">ソース コードの物理的な行の最大文字数は 65535 文字です。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="ba0d8-114">行連結文字を使用すると、論理的なソース コード行が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="ba0d8-115">「[方法:コード内でステートメントを分割および連結する](how-to-break-and-combine-statements-in-code.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-115">See [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="ba0d8-116">**配列の次元:**</span><span class="sxs-lookup"><span data-stu-id="ba0d8-116">**Array Dimensions.**</span></span> <span data-ttu-id="ba0d8-117">配列で宣言できる次元数には上限があります。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="ba0d8-118">これにより、配列要素を指定する際に使用できるインデックスの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="ba0d8-119">「[Visual Basic における配列の次元](../language-features/arrays/array-dimensions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-119">See [Array Dimensions in Visual Basic](../language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="ba0d8-120">**文字列の長さ:**</span><span class="sxs-lookup"><span data-stu-id="ba0d8-120">**String Length.**</span></span> <span data-ttu-id="ba0d8-121">1 つの文字列に格納できる Unicode 文字数には上限があります。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="ba0d8-122">「[文字列型 (String)](../../language-reference/data-types/string-data-type.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-122">See [String Data Type](../../language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="ba0d8-123">**環境文字列の長さ:**</span><span class="sxs-lookup"><span data-stu-id="ba0d8-123">**Environment String Length.**</span></span> <span data-ttu-id="ba0d8-124">コマンド ライン引数として使用される環境文字列の最大文字数は 32768 文字です。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="ba0d8-125">この制限はすべてのプラットフォームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ba0d8-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0d8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba0d8-126">See also</span></span>

- [<span data-ttu-id="ba0d8-127">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="ba0d8-127">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="ba0d8-128">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="ba0d8-128">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
