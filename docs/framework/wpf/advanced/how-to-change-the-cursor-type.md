---
title: '方法: カーソルの種類を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 5c9e6931f6addb62a51e44b06a159d4e7b1e5f8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776676"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="d1b5e-102">方法: カーソルの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="d1b5e-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="d1b5e-103">この例では、特定の要素とアプリケーションでマウスポインターの <xref:System.Windows.Input.Cursor> を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="d1b5e-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ファイルとコード ビハインド ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1b5e-105">例</span><span class="sxs-lookup"><span data-stu-id="d1b5e-105">Example</span></span>  
 <span data-ttu-id="d1b5e-106">希望の <xref:System.Windows.Input.Cursor> を選択する <xref:System.Windows.Controls.ComboBox>、カーソルの変更が 1 つの要素に適用されるかアプリケーション全体に適用されるかを決定する <xref:System.Windows.Controls.RadioButton> の組み、新しいカーソルが適用される <xref:System.Windows.Controls.Border> 要素で構成される、ユーザー インターフェイスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="d1b5e-107">次のコード ビハインドは、<xref:System.Windows.Controls.ComboBox> でカーソルの種類が変更されたときに呼び出される <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="d1b5e-108">switch ステートメントにより、カーソル名がフィルター処理され、*DisplayArea* という名前の <xref:System.Windows.Controls.Border> が <xref:System.Windows.FrameworkElement.Cursor%2A> プロパティに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="d1b5e-109">カーソルの変更が "アプリケーション全体" に設定されている場合、<xref:System.Windows.Input.Mouse.OverrideCursor%2A> プロパティは <xref:System.Windows.Controls.Border> コントロールの <xref:System.Windows.FrameworkElement.Cursor%2A> プロパティに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="d1b5e-110">これにより、アプリケーション全体のカーソルが強制的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d1b5e-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="d1b5e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1b5e-111">See also</span></span>

- [<span data-ttu-id="d1b5e-112">入力の概要</span><span class="sxs-lookup"><span data-stu-id="d1b5e-112">Input Overview</span></span>](input-overview.md)
