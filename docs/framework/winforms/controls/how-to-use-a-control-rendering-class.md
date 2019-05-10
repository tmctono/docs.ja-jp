---
title: '方法: コントロールの描画クラスを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630563"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="8be5c-102">方法: コントロールの描画クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="8be5c-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="8be5c-103">この例では、使用、<xref:System.Windows.Forms.ComboBoxRenderer>ドロップダウン矢印のコンボ ボックス コントロールを描画するクラス。</span><span class="sxs-lookup"><span data-stu-id="8be5c-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="8be5c-104">例から成る、<xref:System.Windows.Forms.Control.OnPaint%2A>単純なカスタム コントロールのメソッド。</span><span class="sxs-lookup"><span data-stu-id="8be5c-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="8be5c-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType>プロパティを使用して、アプリケーション ウィンドウのクライアント領域の視覚スタイルが有効かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8be5c-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="8be5c-106">Visual スタイルが、アクティブな場合、<xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType>メソッドは、visual スタイルは; を使用して、下矢印を表示する場合は、<xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType>メソッドは、従来の Windows スタイルで下矢印を表示します。</span><span class="sxs-lookup"><span data-stu-id="8be5c-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8be5c-107">例</span><span class="sxs-lookup"><span data-stu-id="8be5c-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8be5c-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8be5c-108">Compiling the Code</span></span>  
 <span data-ttu-id="8be5c-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8be5c-109">This example requires:</span></span>  
  
- <span data-ttu-id="8be5c-110">派生したカスタム コントロール、<xref:System.Windows.Forms.Control>クラス。</span><span class="sxs-lookup"><span data-stu-id="8be5c-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="8be5c-111">A<xref:System.Windows.Forms.Form>カスタム コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="8be5c-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="8be5c-112">参照、 <xref:System?displayProperty=nameWithType>、 <xref:System.Drawing?displayProperty=nameWithType>、 <xref:System.Windows.Forms?displayProperty=nameWithType>、および<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="8be5c-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be5c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8be5c-113">See also</span></span>

- [<span data-ttu-id="8be5c-114">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="8be5c-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
