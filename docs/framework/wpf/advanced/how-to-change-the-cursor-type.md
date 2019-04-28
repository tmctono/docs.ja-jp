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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776676"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="b84aa-102">方法: カーソルの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="b84aa-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="b84aa-103">この例では、変更、<xref:System.Windows.Input.Cursor>とアプリケーションの特定の要素をマウス ポインターの。</span><span class="sxs-lookup"><span data-stu-id="b84aa-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="b84aa-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルと分離コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="b84aa-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b84aa-105">例</span><span class="sxs-lookup"><span data-stu-id="b84aa-105">Example</span></span>  
 <span data-ttu-id="b84aa-106">ユーザー インターフェイスを作成するから構成される、<xref:System.Windows.Controls.ComboBox>目的を選択する<xref:System.Windows.Input.Cursor>、1 組の<xref:System.Windows.Controls.RadioButton>カーソルの変更は 1 つの要素のみに適用されますか、アプリケーション全体に適用されますかを判断するオブジェクトと<xref:System.Windows.Controls.Border>これは、新しいカーソルに適用される要素です。</span><span class="sxs-lookup"><span data-stu-id="b84aa-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="b84aa-107">次のコードを作成、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>で、カーソルの種類が変更されたときに呼び出されるイベント ハンドラー、<xref:System.Windows.Controls.ComboBox>します。</span><span class="sxs-lookup"><span data-stu-id="b84aa-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="b84aa-108">Switch ステートメントのセットとカーソルの名前でフィルター処理、<xref:System.Windows.FrameworkElement.Cursor%2A>プロパティを<xref:System.Windows.Controls.Border>名前は*DisplayArea*します。</span><span class="sxs-lookup"><span data-stu-id="b84aa-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="b84aa-109">カーソルの変更は、"全体 Application"に設定されている場合、<xref:System.Windows.Input.Mouse.OverrideCursor%2A>プロパティに設定されて、<xref:System.Windows.FrameworkElement.Cursor%2A>のプロパティ、<xref:System.Windows.Controls.Border>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b84aa-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="b84aa-110">これにより、アプリケーション全体を変更するカーソル。</span><span class="sxs-lookup"><span data-stu-id="b84aa-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="b84aa-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b84aa-111">See also</span></span>

- [<span data-ttu-id="b84aa-112">入力の概要</span><span class="sxs-lookup"><span data-stu-id="b84aa-112">Input Overview</span></span>](input-overview.md)
