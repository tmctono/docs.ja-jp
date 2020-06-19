---
title: '方法: パネルの子を装飾する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923526"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="b58ec-102">方法: パネルの子を装飾する</span><span class="sxs-lookup"><span data-stu-id="b58ec-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="b58ec-103">この例では、指定した <xref:System.Windows.Controls.Panel> の子にプログラムで装飾をバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b58ec-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b58ec-104">例</span><span class="sxs-lookup"><span data-stu-id="b58ec-104">Example</span></span>  
 <span data-ttu-id="b58ec-105"><xref:System.Windows.Controls.Panel> の子に装飾をバインドするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="b58ec-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1. <span data-ttu-id="b58ec-106">新しい <xref:System.Windows.Documents.AdornerLayer> オブジェクトを宣言し、`static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> メソッドを呼び出して、子が装飾対象となる要素の装飾層を検出します。</span><span class="sxs-lookup"><span data-stu-id="b58ec-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2. <span data-ttu-id="b58ec-107">親要素の子を列挙し、<xref:System.Windows.Documents.AdornerLayer.Add%2A> メソッドを呼び出して、装飾を各子要素にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b58ec-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="b58ec-108">次の例では、SimpleCircleAdorner (上図参照) を *myStackPanel* という名前の <xref:System.Windows.Controls.StackPanel> の子にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b58ec-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> <span data-ttu-id="b58ec-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用して、装飾を別の要素にバインドする方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b58ec-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58ec-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b58ec-110">See also</span></span>

- [<span data-ttu-id="b58ec-111">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="b58ec-111">Adorners Overview</span></span>](adorners-overview.md)
