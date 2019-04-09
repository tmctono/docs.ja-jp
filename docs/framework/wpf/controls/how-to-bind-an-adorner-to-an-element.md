---
title: '方法: 要素に装飾をバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 54c9e6dfff2bbf7bfabde523b5d6ae5a623fe733
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194722"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="8b4fc-102">方法: 要素に装飾をバインドする</span><span class="sxs-lookup"><span data-stu-id="8b4fc-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="8b4fc-103">この例は、プログラムで、指定された装飾をバインドする方法を示しています。<xref:System.Windows.UIElement>します。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b4fc-104">例</span><span class="sxs-lookup"><span data-stu-id="8b4fc-104">Example</span></span>  
 <span data-ttu-id="8b4fc-105">特定の装飾をバインドする<xref:System.Windows.UIElement>、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8b4fc-106">呼び出す、`static`メソッド<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>を取得する、<xref:System.Windows.Documents.AdornerLayer>オブジェクト、<xref:System.Windows.UIElement>装飾対象にします。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> <span data-ttu-id="8b4fc-107">指定された、ビジュアル ツリーをウォーク**UIElement**、し、最初に見つかった装飾層を返します。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-107">walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="8b4fc-108">(装飾層が見つからない場合、メソッドにより null が返されます)。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="8b4fc-109">呼び出す、<xref:System.Windows.Documents.AdornerLayer.Add%2A>ターゲットに装飾をバインドするメソッド**UIElement**します。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="8b4fc-110">次の例では、simplecircleadorner に (上図) を参照、<xref:System.Windows.Controls.TextBox>という*myTextBox*します。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="8b4fc-111">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用して、装飾を別の要素にバインドする方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8b4fc-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4fc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b4fc-112">See also</span></span>

- [<span data-ttu-id="8b4fc-113">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="8b4fc-113">Adorners Overview</span></span>](adorners-overview.md)
