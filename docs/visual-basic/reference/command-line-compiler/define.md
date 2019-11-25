---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344760"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="2a5b0-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a5b0-102">-define (Visual Basic)</span></span>
<span data-ttu-id="2a5b0-103">条件付きコンパイル定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a5b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a5b0-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="2a5b0-105">、または</span><span class="sxs-lookup"><span data-stu-id="2a5b0-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a5b0-106">引数</span><span class="sxs-lookup"><span data-stu-id="2a5b0-106">Arguments</span></span>  
  
|<span data-ttu-id="2a5b0-107">用語</span><span class="sxs-lookup"><span data-stu-id="2a5b0-107">Term</span></span>|<span data-ttu-id="2a5b0-108">定義</span><span class="sxs-lookup"><span data-stu-id="2a5b0-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="2a5b0-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-109">Required.</span></span> <span data-ttu-id="2a5b0-110">定義する記号。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="2a5b0-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-111">Optional.</span></span> <span data-ttu-id="2a5b0-112">`symbol` に代入する値。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-112">The value to assign `symbol`.</span></span> <span data-ttu-id="2a5b0-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="2a5b0-114">値が指定されていない場合は、True として処理されます。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a5b0-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a5b0-115">Remarks</span></span>  
 <span data-ttu-id="2a5b0-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="2a5b0-117">このオプションで作成される記号を `#If`...`Then`...`#Else` ディレクティブで使用すると、ソース ファイルを条件付きでコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="2a5b0-118">`-d` は `-define` の省略形です。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="2a5b0-119">記号の定義をコンマで区切ると、`-define` を使用して複数の記号を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="2a5b0-120">Visual Studio 統合開発環境で /define を設定するには</span><span class="sxs-lookup"><span data-stu-id="2a5b0-120">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2a5b0-121">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2a5b0-122">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2a5b0-123">2.  Click the **Compile** tab.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2a5b0-124">3.  Click **Advanced**.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="2a5b0-125">4.  Modify the value in the **Custom Constants** box.</span><span class="sxs-lookup"><span data-stu-id="2a5b0-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a5b0-126">例</span><span class="sxs-lookup"><span data-stu-id="2a5b0-126">Example</span></span>  
 <span data-ttu-id="2a5b0-127">2 つの条件付きコンパイル定数を定義して使用する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a5b0-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="2a5b0-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a5b0-128">See also</span></span>

- [<span data-ttu-id="2a5b0-129">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2a5b0-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2a5b0-130">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2a5b0-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="2a5b0-131">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2a5b0-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="2a5b0-132">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2a5b0-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
