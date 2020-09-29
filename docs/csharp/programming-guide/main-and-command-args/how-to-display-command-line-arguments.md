---
title: コマンド ライン引数を表示する方法 - C# プログラミング ガイド
description: コマンド ライン引数を表示する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195481"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="5a02a-104">コマンド ライン引数を表示する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5a02a-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="5a02a-105">実行可能ファイルに対してコマンド ラインで指定した引数には、`Main` に対する省略可能なパラメーターを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a02a-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="5a02a-106">引数は、文字列の配列の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="5a02a-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="5a02a-107">配列の各要素には、1 つの引数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5a02a-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="5a02a-108">引数間の空白は削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a02a-108">White-space between arguments is removed.</span></span> <span data-ttu-id="5a02a-109">たとえば、架空の実行可能ファイルを呼び出すためのコマンド ラインの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a02a-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="5a02a-110">コマンド ラインでの入力</span><span class="sxs-lookup"><span data-stu-id="5a02a-110">Input on command line</span></span>|<span data-ttu-id="5a02a-111">Main に渡される文字列の配列</span><span class="sxs-lookup"><span data-stu-id="5a02a-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="5a02a-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="5a02a-112">**executable.exe a b c**</span></span>|<span data-ttu-id="5a02a-113">"a"</span><span class="sxs-lookup"><span data-stu-id="5a02a-113">"a"</span></span><br /><br /> <span data-ttu-id="5a02a-114">"b"</span><span class="sxs-lookup"><span data-stu-id="5a02a-114">"b"</span></span><br /><br /> <span data-ttu-id="5a02a-115">"c"</span><span class="sxs-lookup"><span data-stu-id="5a02a-115">"c"</span></span>|  
|<span data-ttu-id="5a02a-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="5a02a-116">**executable.exe one two**</span></span>|<span data-ttu-id="5a02a-117">"one"</span><span class="sxs-lookup"><span data-stu-id="5a02a-117">"one"</span></span><br /><br /> <span data-ttu-id="5a02a-118">"two"</span><span class="sxs-lookup"><span data-stu-id="5a02a-118">"two"</span></span>|  
|<span data-ttu-id="5a02a-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="5a02a-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="5a02a-120">"one two"</span><span class="sxs-lookup"><span data-stu-id="5a02a-120">"one two"</span></span><br /><br /> <span data-ttu-id="5a02a-121">"three"</span><span class="sxs-lookup"><span data-stu-id="5a02a-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="5a02a-122">Visual Studio でアプリケーションを実行する場合は、[[デバッグ] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/debug-page-project-designer) でコマンド ライン引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a02a-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a02a-123">例</span><span class="sxs-lookup"><span data-stu-id="5a02a-123">Example</span></span>  

 <span data-ttu-id="5a02a-124">この例は、コマンド ライン アプリケーションに渡されるコマンド ライン引数を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a02a-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="5a02a-125">次の出力は、上の表の最初のエントリに対するものです。</span><span class="sxs-lookup"><span data-stu-id="5a02a-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="5a02a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a02a-126">See also</span></span>

- [<span data-ttu-id="5a02a-127">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5a02a-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5a02a-128">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="5a02a-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="5a02a-129">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="5a02a-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="5a02a-130">Main() の戻り値</span><span class="sxs-lookup"><span data-stu-id="5a02a-130">Main() Return Values</span></span>](./main-return-values.md)
