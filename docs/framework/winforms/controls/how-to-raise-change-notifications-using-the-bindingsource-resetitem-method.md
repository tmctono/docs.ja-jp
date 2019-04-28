---
title: '方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 68073f245e1a2eb18a277d7011ca0183dabb3724
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913147"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="16869-102">方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="16869-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="16869-103">コントロールのデータ ソースの中には、項目が変更、追加、または削除されても変更通知が発生しないものがあります。</span><span class="sxs-lookup"><span data-stu-id="16869-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="16869-104"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用すると、そのようなデータ ソースをバインドし、コードから変更通知を発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="16869-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16869-105">例</span><span class="sxs-lookup"><span data-stu-id="16869-105">Example</span></span>  
 <span data-ttu-id="16869-106">このフォームは、<xref:System.Windows.Forms.BindingSource> コンポーネントを使用してリストを <xref:System.Windows.Forms.DataGridView> コントロールにバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="16869-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="16869-107">リストは変更通知を発生しないため、リスト内の項目が変更されると、<xref:System.Windows.Forms.BindingSource> の <xref:System.Windows.Forms.BindingSource.ResetItem%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="16869-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="16869-108">.</span><span class="sxs-lookup"><span data-stu-id="16869-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16869-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="16869-109">Compiling the Code</span></span>  
 <span data-ttu-id="16869-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16869-110">This example requires:</span></span>  
  
- <span data-ttu-id="16869-111">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="16869-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="16869-112">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16869-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="16869-113">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="16869-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16869-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="16869-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="16869-115">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16869-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="16869-116">方法: Windows フォーム コントロールを型にバインドします。</span><span class="sxs-lookup"><span data-stu-id="16869-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
