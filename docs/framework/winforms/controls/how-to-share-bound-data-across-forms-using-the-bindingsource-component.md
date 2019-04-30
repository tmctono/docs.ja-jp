---
title: '方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 19505c690728147d2a67c26371e1cea4c281ab08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013050"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="422f2-102">方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する</span><span class="sxs-lookup"><span data-stu-id="422f2-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="422f2-103"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用してフォーム間でデータを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="422f2-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="422f2-104">たとえば、データ ソースのデータを集計する 1 つの読み取り専用のフォームと、データ ソース内の現在選択されているアイテムについての詳細情報を含む別の編集可能なフォームを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="422f2-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="422f2-105">この例は、このシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="422f2-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="422f2-106">例</span><span class="sxs-lookup"><span data-stu-id="422f2-106">Example</span></span>  
 <span data-ttu-id="422f2-107">次のコード例は、<xref:System.Windows.Forms.BindingSource> およびフォーム間でバインドされたデータを共有する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="422f2-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="422f2-108">この例で、共有された <xref:System.Windows.Forms.BindingSource> が子フォームのコンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="422f2-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="422f2-109">子フォームでは、メイン フォームで現在選択されているアイテムのデータをユーザーが編集することができます。</span><span class="sxs-lookup"><span data-stu-id="422f2-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="422f2-110">例の <xref:System.Windows.Forms.BindingSource> コンポーネントの <xref:System.Windows.Forms.BindingSource.BindingComplete> イベントは、2 つの形式が同期を保つために処理されます。</span><span class="sxs-lookup"><span data-stu-id="422f2-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="422f2-111">これ行う理由の詳細については、「[方法。複数のコントロールと同じデータ ソースにバインドが同期を保つ](../multiple-controls-bound-to-data-source-synchronized.md)します。</span><span class="sxs-lookup"><span data-stu-id="422f2-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="422f2-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="422f2-112">Compiling the Code</span></span>  
 <span data-ttu-id="422f2-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="422f2-113">This example requires:</span></span>  
  
- <span data-ttu-id="422f2-114">System、System.Windows.Forms、System.Drawing、System.Data、および System.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="422f2-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="422f2-115">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="422f2-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="422f2-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="422f2-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422f2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="422f2-117">See also</span></span>

- [<span data-ttu-id="422f2-118">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="422f2-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="422f2-119">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="422f2-119">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="422f2-120">方法: エラーとデータ バインドで発生する例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="422f2-120">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
