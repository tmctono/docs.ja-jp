---
title: '方法: Windows フォーム コントロールをファクトリ オブジェクトにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2de892d94afdfcdc580d20f90fb60ebabf4a9b37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761417"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="327d3-102">方法: Windows フォーム コントロールをファクトリ オブジェクトにバインドする</span><span class="sxs-lookup"><span data-stu-id="327d3-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="327d3-103">データをやり取りするコントロールを作成している際に、他のオブジェクトを生成するオブジェクトやメソッドにコントロールをバインドすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="327d3-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="327d3-104">このようなオブジェクトやメソッドは、ファクトリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="327d3-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="327d3-105">たとえば、データ ソースがメモリまたは型内のオブジェクトではなく、メソッドの呼び出しからの戻り値の場合があります。</span><span class="sxs-lookup"><span data-stu-id="327d3-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="327d3-106">ソースがコレクションを返す限り、コントロールをこの種類のデータ ソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="327d3-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="327d3-107"><xref:System.Windows.Forms.BindingSource> コントロールを使用して、コントロールをファクトリ オブジェクトに簡単にバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="327d3-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="327d3-108">例</span><span class="sxs-lookup"><span data-stu-id="327d3-108">Example</span></span>  
 <span data-ttu-id="327d3-109">次の例では、<xref:System.Windows.Forms.BindingSource> コントロールを使用して、<xref:System.Windows.Forms.DataGridView> コントロールをファクトリ メソッドにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="327d3-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="327d3-110">ファクトリ メソッドの名前は `GetOrdersByCustomerId` であり、Northwind データベースで、特定の顧客のすべての注文を返します。</span><span class="sxs-lookup"><span data-stu-id="327d3-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="327d3-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="327d3-111">Compiling the Code</span></span>  
 <span data-ttu-id="327d3-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="327d3-112">This example requires:</span></span>  
  
- <span data-ttu-id="327d3-113">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="327d3-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="327d3-114">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="327d3-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="327d3-115">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="327d3-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="327d3-116">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="327d3-117">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="327d3-117">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="327d3-118">方法: Windows フォーム コントロールを型にバインドします。</span><span class="sxs-lookup"><span data-stu-id="327d3-118">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
