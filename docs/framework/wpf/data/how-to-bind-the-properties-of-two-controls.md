---
title: '方法 : 2 つのコントロールのプロパティをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974813"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="8aa42-102">方法 : 2 つのコントロールのプロパティをバインドする</span><span class="sxs-lookup"><span data-stu-id="8aa42-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="8aa42-103">この例では、<xref:System.Windows.Data.Binding.ElementName%2A> プロパティを使用して、インスタンス化されたコントロールのプロパティを別のコントロールのプロパティにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8aa42-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="8aa42-104">例</span><span class="sxs-lookup"><span data-stu-id="8aa42-104">Example</span></span>

<span data-ttu-id="8aa42-105">次の例は、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Panel.Background%2A> プロパティを <xref:System.Windows.Controls.ComboBox>の[SelectedItem](xref:System.Windows.Controls.ContentControl.Content%2A)プロパティにバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8aa42-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="8aa42-106">この例をレンダリングすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8aa42-106">When this example is rendered it looks like the following:</span></span>

![緑色の値が選択されたコンボボックスと緑色の四角形を示すスクリーンショット。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="8aa42-108">バインディングターゲットプロパティ (この例では <xref:System.Windows.Controls.Panel.Background%2A> プロパティ) は依存関係プロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aa42-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="8aa42-109">詳しくは、「[データ バインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8aa42-109">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8aa42-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aa42-110">See also</span></span>

- [<span data-ttu-id="8aa42-111">バインディング ソースを指定する</span><span class="sxs-lookup"><span data-stu-id="8aa42-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="8aa42-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8aa42-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
