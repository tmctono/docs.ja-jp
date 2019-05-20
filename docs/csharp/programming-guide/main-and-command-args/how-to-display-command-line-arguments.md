---
title: '方法: コマンド ライン引数を表示する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: c88219d03d40c814338a1b09ccd37cfc03c2d577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881013"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="a9c94-102">方法: コマンド ライン引数を表示する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a9c94-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="a9c94-103">実行可能ファイルに対してコマンド ラインで指定した引数には、省略可能なパラメーターを介して `Main` からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a9c94-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="a9c94-104">引数は、文字列の配列の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a9c94-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="a9c94-105">配列の各要素には、1 つの引数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a9c94-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="a9c94-106">引数間の空白は削除されます。</span><span class="sxs-lookup"><span data-stu-id="a9c94-106">White-space between arguments is removed.</span></span> <span data-ttu-id="a9c94-107">たとえば、架空の実行可能ファイルを呼び出すためのコマンド ラインの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9c94-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="a9c94-108">コマンドラインでの入力</span><span class="sxs-lookup"><span data-stu-id="a9c94-108">Input on Command-line</span></span>|<span data-ttu-id="a9c94-109">Main に渡される文字列の配列</span><span class="sxs-lookup"><span data-stu-id="a9c94-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="a9c94-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="a9c94-110">**executable.exe a b c**</span></span>|<span data-ttu-id="a9c94-111">"a"</span><span class="sxs-lookup"><span data-stu-id="a9c94-111">"a"</span></span><br /><br /> <span data-ttu-id="a9c94-112">"b"</span><span class="sxs-lookup"><span data-stu-id="a9c94-112">"b"</span></span><br /><br /> <span data-ttu-id="a9c94-113">"c"</span><span class="sxs-lookup"><span data-stu-id="a9c94-113">"c"</span></span>|  
|<span data-ttu-id="a9c94-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="a9c94-114">**executable.exe one two**</span></span>|<span data-ttu-id="a9c94-115">"one"</span><span class="sxs-lookup"><span data-stu-id="a9c94-115">"one"</span></span><br /><br /> <span data-ttu-id="a9c94-116">"two"</span><span class="sxs-lookup"><span data-stu-id="a9c94-116">"two"</span></span>|  
|<span data-ttu-id="a9c94-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="a9c94-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="a9c94-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="a9c94-118">"one two"</span></span><br /><br /> <span data-ttu-id="a9c94-119">"three"</span><span class="sxs-lookup"><span data-stu-id="a9c94-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a9c94-120">Visual Studio でアプリケーションを実行する場合は、[[デバッグ] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/debug-page-project-designer) でコマンド ライン引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9c94-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c94-121">例</span><span class="sxs-lookup"><span data-stu-id="a9c94-121">Example</span></span>  
 <span data-ttu-id="a9c94-122">この例は、コマンド ライン アプリケーションに渡されるコマンド ライン引数を示しています。</span><span class="sxs-lookup"><span data-stu-id="a9c94-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="a9c94-123">次の出力は、上の表の最初のエントリに対するものです。</span><span class="sxs-lookup"><span data-stu-id="a9c94-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a9c94-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9c94-124">See also</span></span>

- [<span data-ttu-id="a9c94-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a9c94-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a9c94-126">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="a9c94-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="a9c94-127">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="a9c94-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="a9c94-128">Main() の戻り値</span><span class="sxs-lookup"><span data-stu-id="a9c94-128">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
