---
title: '方法 : コードでバインディングを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458850"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="ec08f-102">方法 : コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="ec08f-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="ec08f-103">この例では、コードで <xref:System.Windows.Data.Binding> を作成して設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ec08f-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec08f-104">例</span><span class="sxs-lookup"><span data-stu-id="ec08f-104">Example</span></span>  
 <span data-ttu-id="ec08f-105"><xref:System.Windows.FrameworkElement> クラスと <xref:System.Windows.FrameworkContentElement> クラスはどちらも `SetBinding` メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="ec08f-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="ec08f-106">これらのクラスのいずれかを継承する要素をバインドする場合は、<xref:System.Windows.FrameworkElement.SetBinding%2A> メソッドを直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ec08f-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="ec08f-107">次の例では、`MyDataProperty`という名前のプロパティを含む、`MyData`という名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec08f-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="ec08f-108">バインドオブジェクトを作成してバインディングのソースを設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="ec08f-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="ec08f-109">この例では、<xref:System.Windows.FrameworkElement.SetBinding%2A> を使用して、<xref:System.Windows.Controls.TextBlock> コントロールである `myText`の <xref:System.Windows.Controls.TextBlock.Text%2A> プロパティを `MyDataProperty`にバインドします。</span><span class="sxs-lookup"><span data-stu-id="ec08f-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="ec08f-110">完全なコードサンプルについては、「[コードのみのバインディングのサンプル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec08f-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="ec08f-111"><xref:System.Windows.FrameworkElement.SetBinding%2A>を呼び出す代わりに、<xref:System.Windows.Data.BindingOperations> クラスの <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 静的メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec08f-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="ec08f-112">次の例では、`myText` を `myDataProperty`にバインドするために、<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> ではなく <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ec08f-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="ec08f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec08f-113">See also</span></span>

- [<span data-ttu-id="ec08f-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="ec08f-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ec08f-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="ec08f-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
