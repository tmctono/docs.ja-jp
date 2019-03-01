---
title: -定義 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: c21223cc353b7a4614511aa97340c6bc5d61e70e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200658"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="67a43-102">-定義 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67a43-102">-define (Visual Basic)</span></span>
<span data-ttu-id="67a43-103">条件付きコンパイル定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="67a43-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a43-104">構文</span><span class="sxs-lookup"><span data-stu-id="67a43-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="67a43-105">引数</span><span class="sxs-lookup"><span data-stu-id="67a43-105">Arguments</span></span>  
  
|<span data-ttu-id="67a43-106">用語</span><span class="sxs-lookup"><span data-stu-id="67a43-106">Term</span></span>|<span data-ttu-id="67a43-107">定義</span><span class="sxs-lookup"><span data-stu-id="67a43-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="67a43-108">必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="67a43-108">Required.</span></span> <span data-ttu-id="67a43-109">定義する記号。</span><span class="sxs-lookup"><span data-stu-id="67a43-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="67a43-110">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="67a43-110">Optional.</span></span> <span data-ttu-id="67a43-111">
  `symbol\` に代入する値。</span><span class="sxs-lookup"><span data-stu-id="67a43-111">The value to assign `symbol`.</span></span> <span data-ttu-id="67a43-112">場合`value`文字列で、シーケンスのバック スラッシュ/引用符で囲みます (\\") 引用符の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="67a43-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="67a43-113">値が指定されていない場合は、True として処理されます。</span><span class="sxs-lookup"><span data-stu-id="67a43-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67a43-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="67a43-114">Remarks</span></span>  
 <span data-ttu-id="67a43-115">`-define`オプションを使用すると同様の効果には、`#Const`プリプロセッサ ディレクティブで定義された定数を除く、ソース ファイル内`-define`をパブリックにして、プロジェクト内のすべてのファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="67a43-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="67a43-116">このオプションで作成される記号を `#If`...`Then`...`#Else` ディレクティブで使用すると、ソース ファイルを条件付きでコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="67a43-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="67a43-117">`-d` は `-define` の省略形です。</span><span class="sxs-lookup"><span data-stu-id="67a43-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="67a43-118">記号の定義をコンマで区切ると、`-define` を使用して複数の記号を定義できます。</span><span class="sxs-lookup"><span data-stu-id="67a43-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="67a43-119">Visual Studio 統合開発環境で /define を設定するには</span><span class="sxs-lookup"><span data-stu-id="67a43-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="67a43-120">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="67a43-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="67a43-121">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67a43-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="67a43-122">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67a43-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="67a43-123">3.**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67a43-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="67a43-124">4.値を変更、**カスタム定数**ボックス。</span><span class="sxs-lookup"><span data-stu-id="67a43-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67a43-125">例</span><span class="sxs-lookup"><span data-stu-id="67a43-125">Example</span></span>  
 <span data-ttu-id="67a43-126">2 つの条件付きコンパイル定数を定義して使用する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67a43-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="67a43-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a43-127">See also</span></span>
- [<span data-ttu-id="67a43-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="67a43-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="67a43-129">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="67a43-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="67a43-130">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="67a43-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="67a43-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="67a43-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
