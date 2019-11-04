---
title: '方法 : 2 つのコントロールのプロパティをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459170"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="a36f9-102">方法 : 2 つのコントロールのプロパティをバインドする</span><span class="sxs-lookup"><span data-stu-id="a36f9-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="a36f9-103">この例では、<xref:System.Windows.Data.Binding.ElementName%2A> プロパティを使用して、インスタンス化されたコントロールのプロパティを別のコントロールのプロパティにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a36f9-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a36f9-104">例</span><span class="sxs-lookup"><span data-stu-id="a36f9-104">Example</span></span>  
 <span data-ttu-id="a36f9-105">次の例は、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Panel.Background%2A> プロパティを <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>にバインドする方法を示しています。<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="a36f9-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="a36f9-106"><xref:System.Windows.Controls.ComboBox>のプロパティ:</span><span class="sxs-lookup"><span data-stu-id="a36f9-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="a36f9-107">この例をレンダリングすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a36f9-107">When this example is rendered it looks like the following:</span></span>  
  
![緑色の値が選択されたコンボボックスと緑色の四角形を示すスクリーンショット。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="a36f9-109">バインディングターゲットプロパティ (この例では <xref:System.Windows.Controls.Panel.Background%2A> プロパティ) は依存関係プロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36f9-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="a36f9-110">詳しくは、「[データ バインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a36f9-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36f9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a36f9-111">See also</span></span>

- [<span data-ttu-id="a36f9-112">バインディング ソースを指定する</span><span class="sxs-lookup"><span data-stu-id="a36f9-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="a36f9-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="a36f9-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
