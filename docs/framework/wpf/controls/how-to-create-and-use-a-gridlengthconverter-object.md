---
title: '方法: GridLengthConverter オブジェクトを作成および使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050988"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="4cd35-102">方法: GridLengthConverter オブジェクトを作成および使用する</span><span class="sxs-lookup"><span data-stu-id="4cd35-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="4cd35-103">例</span><span class="sxs-lookup"><span data-stu-id="4cd35-103">Example</span></span>  
 <span data-ttu-id="4cd35-104"><xref:System.Windows.GridLengthConverter> のインスタンスを作成し、使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cd35-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="4cd35-105">この例では、`changeCol` という名称のカスタム メソッドが定義されます。<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> を <xref:System.Windows.GridLength> のインスタンスに変換する <xref:System.Windows.GridLengthConverter> に <xref:System.Windows.Controls.ListBoxItem> がこのメソッドによって渡されます。</span><span class="sxs-lookup"><span data-stu-id="4cd35-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="4cd35-106">この変換後の値が次に、<xref:System.Windows.Controls.ColumnDefinition> 要素の <xref:System.Windows.Controls.ColumnDefinition.Width%2A> プロパティの値として返されます。</span><span class="sxs-lookup"><span data-stu-id="4cd35-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="4cd35-107">この例では、`changeColVal` という名前の 2 つ目のカスタム メソッドも定義されています。</span><span class="sxs-lookup"><span data-stu-id="4cd35-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="4cd35-108">このカスタム メソッドでは、<xref:System.Windows.Controls.Slider> の <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> が <xref:System.String> に変換され、その値が要素の <xref:System.Windows.Controls.ColumnDefinition.Width%2A> として <xref:System.Windows.Controls.ColumnDefinition> に返されます。</span><span class="sxs-lookup"><span data-stu-id="4cd35-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="4cd35-109">別の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ファイルで <xref:System.Windows.Controls.ListBoxItem> のコンテンツが定義されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4cd35-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4cd35-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cd35-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
