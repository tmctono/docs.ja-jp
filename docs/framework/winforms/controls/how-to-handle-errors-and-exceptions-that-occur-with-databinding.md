---
title: '方法: データ バインドで発生するエラーと例外を処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 709db2a98074e3322adad8b1275b3c4418c14636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941272"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="1f0e7-102">方法: データ バインドで発生するエラーと例外を処理する</span><span class="sxs-lookup"><span data-stu-id="1f0e7-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="1f0e7-103">基になるビジネス オブジェクトをコントロールにバインドするときに、それらのビジネス オブジェクトで例外やエラーが発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="1f0e7-104">特定の <xref:System.Windows.Forms.Binding> コンポーネント、<xref:System.Windows.Forms.BindingSource> コンポーネント、または <xref:System.Windows.Forms.CurrencyManager> コンポーネントの <xref:System.Windows.Forms.Binding.BindingComplete> イベントを処理することにより、これらのエラーや例外をインターセプトし、回復したり、エラー情報をユーザーに渡したりできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f0e7-105">例</span><span class="sxs-lookup"><span data-stu-id="1f0e7-105">Example</span></span>  
 <span data-ttu-id="1f0e7-106">データ バインディング操作時に発生するエラーと例外を処理する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="1f0e7-107">ここでは、<xref:System.Windows.Forms.Binding> オブジェクトの <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> イベントを処理してエラーをインターセプトする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="1f0e7-108">このイベントを処理してエラーと例外をインターセプトするには、バインディングの書式設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="1f0e7-109">バインディングの書式設定は、バインディングの作成時やバインディング コレクションへの追加時に有効にできます。また、<xref:System.Windows.Forms.Binding.FormattingEnabled%2A> プロパティを `true` に設定すると有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="1f0e7-110">コードの実行時に、部品名に空の文字列が入力されるか、部品番号に 100 未満の値が入力されると、メッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="1f0e7-111">これは、これらのテキスト ボックス バインディングの <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> イベントを処理した結果です。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f0e7-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="1f0e7-112">Compiling the Code</span></span>  
 <span data-ttu-id="1f0e7-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-113">This example requires:</span></span>  
  
- <span data-ttu-id="1f0e7-114">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1f0e7-115">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1f0e7-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e7-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0e7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f0e7-117">See also</span></span>

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [<span data-ttu-id="1f0e7-118">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f0e7-118">BindingSource Component</span></span>](bindingsource-component.md)
