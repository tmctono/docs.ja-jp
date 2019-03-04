---
title: '方法: foreach を使用してコマンド ライン引数にアクセスする - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 5813ad573e89886ba991ca8cbcebb7232af05821
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971677"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="7fde7-102">方法: foreach を使用してコマンド ライン引数にアクセスする (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="7fde7-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="7fde7-103">配列の反復処理には、この例で示すように [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ステートメントを使用する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="7fde7-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="7fde7-104">`foreach` ステートメントは、配列、.NET Framework コレクション クラス、または <xref:System.Collections.IEnumerable> インターフェイスを実装する任意のクラスや構造体の反復処理に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fde7-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fde7-105">Visual Studio でアプリケーションを実行する場合、「[[デバッグ] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/debug-page-project-designer)」のコマンド ライン引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7fde7-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fde7-106">例</span><span class="sxs-lookup"><span data-stu-id="7fde7-106">Example</span></span>  
 <span data-ttu-id="7fde7-107">この例では、`foreach` を使用したコマンド ライン引数の出力方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7fde7-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class2.cs#10)]  
  
 [!code-csharp[csProgGuideMain#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="7fde7-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fde7-108">See also</span></span>

- <xref:System.Array>
- <xref:System.Collections>
- [<span data-ttu-id="7fde7-109">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="7fde7-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="7fde7-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7fde7-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7fde7-111">foreach、in</span><span class="sxs-lookup"><span data-stu-id="7fde7-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="7fde7-112">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="7fde7-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="7fde7-113">方法: コマンド ライン引数を表示する</span><span class="sxs-lookup"><span data-stu-id="7fde7-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="7fde7-114">Main() の戻り値</span><span class="sxs-lookup"><span data-stu-id="7fde7-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
