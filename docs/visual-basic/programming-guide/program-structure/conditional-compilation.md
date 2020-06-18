---
title: 条件付きコンパイル
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 19a2c70941a9a72574f7e624743def74b80c4e39
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347460"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="3406e-102">Visual Basic での条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="3406e-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="3406e-103">"*条件付きコンパイル*" では、プログラム内の特定のコード ブロックが選択的にコンパイルされ、他のコード ブロックは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3406e-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="3406e-104">たとえば、同じプログラミング タスクに対するさまざまなアプローチの速度を比較するデバッグ ステートメントを記述したり、複数の言語用にアプリケーションをローカライズしたりできます。</span><span class="sxs-lookup"><span data-stu-id="3406e-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="3406e-105">条件付きコンパイル ステートメントは、実行時ではなく、コンパイル時に実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3406e-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="3406e-106">条件付きでコンパイルされるコード ブロックは、`#If...Then...#Else` ディレクティブで示します。</span><span class="sxs-lookup"><span data-stu-id="3406e-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="3406e-107">たとえば、同じソース コードから同じアプリケーションのフランス語バージョンとドイツ語バージョンを作成するには、事前定義された定数 `FrenchVersion` と `GermanVersion` を使用して、プラットフォーム固有のコード セグメントを `#If...Then` ステートメントに埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="3406e-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="3406e-108">次の例はその方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3406e-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="3406e-109">コンパイル時に `FrenchVersion` 条件付きコンパイル定数の値を `True` に設定すると、フランス語バージョンの条件付きコードがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3406e-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="3406e-110">`GermanVersion` 定数の値を `True` に設定すると、コンパイラはドイツ語バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3406e-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="3406e-111">どちらも `True` に設定されていない場合は、最後の `Else` ブロックのコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3406e-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3406e-112">コードが現在のブランチに含まれていない場合、コードを編集し、条件付きコンパイル ディレクティブを使用したときに、オートコンプリートは機能しません。</span><span class="sxs-lookup"><span data-stu-id="3406e-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="3406e-113">条件付きコンパイル定数の宣言</span><span class="sxs-lookup"><span data-stu-id="3406e-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="3406e-114">条件付きコンパイル定数は、次の 3 つの方法のいずれかで設定できます。</span><span class="sxs-lookup"><span data-stu-id="3406e-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="3406e-115">**プロジェクト デザイナー**内</span><span class="sxs-lookup"><span data-stu-id="3406e-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="3406e-116">コマンド ライン (コマンド ライン コンパイラを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="3406e-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="3406e-117">コード内</span><span class="sxs-lookup"><span data-stu-id="3406e-117">In your code</span></span>  
  
 <span data-ttu-id="3406e-118">条件付きコンパイル定数には特別なスコープがあり、標準コードからアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3406e-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="3406e-119">条件付きコンパイル定数のスコープは、設定方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3406e-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="3406e-120">次の表に、上記の 3 つの方法をそれぞれ使用して宣言された定数のスコープを示します。</span><span class="sxs-lookup"><span data-stu-id="3406e-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="3406e-121">定数の設定方法</span><span class="sxs-lookup"><span data-stu-id="3406e-121">How constant is set</span></span>|<span data-ttu-id="3406e-122">定数のスコープ</span><span class="sxs-lookup"><span data-stu-id="3406e-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="3406e-123">**プロジェクト デザイナー**</span><span class="sxs-lookup"><span data-stu-id="3406e-123">**Project Designer**</span></span>|<span data-ttu-id="3406e-124">プロジェクト内のすべてのファイルに対してパブリック</span><span class="sxs-lookup"><span data-stu-id="3406e-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="3406e-125">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="3406e-125">Command line</span></span>|<span data-ttu-id="3406e-126">コマンド ライン コンパイラに渡されるすべてのファイルに対してパブリック</span><span class="sxs-lookup"><span data-stu-id="3406e-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="3406e-127">コード内の `#Const` ステートメント</span><span class="sxs-lookup"><span data-stu-id="3406e-127">`#Const` statement in code</span></span>|<span data-ttu-id="3406e-128">これが宣言されているファイルに対してプライベート</span><span class="sxs-lookup"><span data-stu-id="3406e-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="3406e-129">プロジェクト デザイナーで定数を設定するには</span><span class="sxs-lookup"><span data-stu-id="3406e-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="3406e-130">-   実行可能ファイルを作成する前に、「[プロジェクトおよびソリューションのプロパティの管理](/visualstudio/ide/managing-project-and-solution-properties)」に記載されている手順に従って、**プロジェクト デザイナー**で定数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3406e-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="3406e-131">コマンド ラインで定数を設定するには</span><span class="sxs-lookup"><span data-stu-id="3406e-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="3406e-132">-   次の例のように、 **-d** スイッチを使用して条件付きコンパイル定数を入力します。</span><span class="sxs-lookup"><span data-stu-id="3406e-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="3406e-133">**-d** スイッチと最初の定数の間にスペースは不要です。</span><span class="sxs-lookup"><span data-stu-id="3406e-133">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="3406e-134">詳細については、「[-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3406e-134">For more information, see [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="3406e-135">コマンド ラインの宣言は、**プロジェクト デザイナー**で入力された宣言をオーバーライドしますが、それらを消去するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3406e-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="3406e-136">**プロジェクト デザイナー**で設定した引数は、後続のコンパイルでも有効です。</span><span class="sxs-lookup"><span data-stu-id="3406e-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="3406e-137">コード自体に定数を記述する場合、定数のスコープはそれらが宣言されているモジュール全体であるため、配置に関して厳密な規則はありません。</span><span class="sxs-lookup"><span data-stu-id="3406e-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="3406e-138">コードで定数を設定するには</span><span class="sxs-lookup"><span data-stu-id="3406e-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="3406e-139">-   定数が使用されるモジュールの宣言ブロックに定数を配置します。</span><span class="sxs-lookup"><span data-stu-id="3406e-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="3406e-140">これにより、コードが整理され、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="3406e-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="3406e-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3406e-141">Related Topics</span></span>  
  
|<span data-ttu-id="3406e-142">Title</span><span class="sxs-lookup"><span data-stu-id="3406e-142">Title</span></span>|<span data-ttu-id="3406e-143">説明</span><span class="sxs-lookup"><span data-stu-id="3406e-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="3406e-144">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="3406e-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="3406e-145">コードを読みやすくし、管理しやすくするための推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="3406e-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="3406e-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="3406e-146">Reference</span></span>  
 [<span data-ttu-id="3406e-147">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3406e-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="3406e-148">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3406e-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="3406e-149">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3406e-149">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
