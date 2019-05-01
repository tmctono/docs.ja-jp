---
title: '方法: 2 つのコントロールのプロパティをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809539"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="1d45e-102">方法: 2 つのコントロールのプロパティをバインドする</span><span class="sxs-lookup"><span data-stu-id="1d45e-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="1d45e-103">この例を使用して別の 1 つのインスタンス化されたコントロールのプロパティをバインドする方法を示しています、<xref:System.Windows.Data.Binding.ElementName%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1d45e-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d45e-104">例</span><span class="sxs-lookup"><span data-stu-id="1d45e-104">Example</span></span>  
 <span data-ttu-id="1d45e-105">次の例では、バインドする方法を示しています、<xref:System.Windows.Controls.Panel.Background%2A>のプロパティを<xref:System.Windows.Controls.Canvas>を<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>します。<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="1d45e-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="1d45e-106">プロパティを<xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="1d45e-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="1d45e-107">この例をレンダリングすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d45e-107">When this example is rendered it looks like the following:</span></span>  
  
![緑の値のボックスをオンし、緑色の四角形にコンボを示すスクリーン ショット。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="1d45e-109">バインディング ターゲット プロパティ (この例で、<xref:System.Windows.Controls.Panel.Background%2A>プロパティ) 依存関係プロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d45e-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="1d45e-110">詳しくは、「 [データ バインディングの概要](data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d45e-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d45e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d45e-111">See also</span></span>

- [<span data-ttu-id="1d45e-112">バインディング ソースを指定する</span><span class="sxs-lookup"><span data-stu-id="1d45e-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="1d45e-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1d45e-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
