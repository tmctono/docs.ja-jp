---
title: コマンド ライン引数を表示する方法 - C# プログラミング ガイド
description: コマンド ライン引数を表示する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 1ac5dc5a5f4e974c9202d2ce23f61071494e1977
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381815"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="c44b9-104">コマンド ライン引数を表示する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c44b9-104">How to display command-line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="c44b9-105">実行可能ファイルに対してコマンド ラインで指定した引数には、`Main` に対する省略可能なパラメーターを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c44b9-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="c44b9-106">引数は、文字列の配列の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="c44b9-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="c44b9-107">配列の各要素には、1 つの引数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c44b9-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="c44b9-108">引数間の空白は削除されます。</span><span class="sxs-lookup"><span data-stu-id="c44b9-108">White-space between arguments is removed.</span></span> <span data-ttu-id="c44b9-109">たとえば、架空の実行可能ファイルを呼び出すためのコマンド ラインの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c44b9-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="c44b9-110">コマンド ラインでの入力</span><span class="sxs-lookup"><span data-stu-id="c44b9-110">Input on command line</span></span>|<span data-ttu-id="c44b9-111">Main に渡される文字列の配列</span><span class="sxs-lookup"><span data-stu-id="c44b9-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="c44b9-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="c44b9-112">**executable.exe a b c**</span></span>|<span data-ttu-id="c44b9-113">"a"</span><span class="sxs-lookup"><span data-stu-id="c44b9-113">"a"</span></span><br /><br /> <span data-ttu-id="c44b9-114">"b"</span><span class="sxs-lookup"><span data-stu-id="c44b9-114">"b"</span></span><br /><br /> <span data-ttu-id="c44b9-115">"c"</span><span class="sxs-lookup"><span data-stu-id="c44b9-115">"c"</span></span>|  
|<span data-ttu-id="c44b9-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="c44b9-116">**executable.exe one two**</span></span>|<span data-ttu-id="c44b9-117">"one"</span><span class="sxs-lookup"><span data-stu-id="c44b9-117">"one"</span></span><br /><br /> <span data-ttu-id="c44b9-118">"two"</span><span class="sxs-lookup"><span data-stu-id="c44b9-118">"two"</span></span>|  
|<span data-ttu-id="c44b9-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="c44b9-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="c44b9-120">"one two"</span><span class="sxs-lookup"><span data-stu-id="c44b9-120">"one two"</span></span><br /><br /> <span data-ttu-id="c44b9-121">"three"</span><span class="sxs-lookup"><span data-stu-id="c44b9-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c44b9-122">Visual Studio でアプリケーションを実行する場合は、[[デバッグ] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/debug-page-project-designer) でコマンド ライン引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c44b9-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c44b9-123">例</span><span class="sxs-lookup"><span data-stu-id="c44b9-123">Example</span></span>  
 <span data-ttu-id="c44b9-124">この例は、コマンド ライン アプリケーションに渡されるコマンド ライン引数を示しています。</span><span class="sxs-lookup"><span data-stu-id="c44b9-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="c44b9-125">次の出力は、上の表の最初のエントリに対するものです。</span><span class="sxs-lookup"><span data-stu-id="c44b9-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c44b9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c44b9-126">See also</span></span>

- [<span data-ttu-id="c44b9-127">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c44b9-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c44b9-128">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="c44b9-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="c44b9-129">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="c44b9-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="c44b9-130">Main() の戻り値</span><span class="sxs-lookup"><span data-stu-id="c44b9-130">Main() Return Values</span></span>](./main-return-values.md)
