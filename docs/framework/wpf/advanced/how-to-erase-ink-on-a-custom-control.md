---
title: '方法: カスタム コントロールでインクを消去する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365894"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="fb0e9-102">方法: カスタム コントロールでインクを消去する</span><span class="sxs-lookup"><span data-stu-id="fb0e9-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="fb0e9-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester>現在描画ストロークに別のストロークと交差しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fb0e9-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="fb0e9-104">ストロークの一部を消去するユーザーをできるようにするコントロールを作成するのに便利ですが、方法、ユーザーが、<xref:System.Windows.Controls.InkCanvas>ときに、<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>に設定されている<xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>します。</span><span class="sxs-lookup"><span data-stu-id="fb0e9-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb0e9-105">例</span><span class="sxs-lookup"><span data-stu-id="fb0e9-105">Example</span></span>  
 <span data-ttu-id="fb0e9-106">次の例では、ユーザーがストロークの一部を消去できるようにするカスタム コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb0e9-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="fb0e9-107">この例では、初期化時に、インクを格納しているコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb0e9-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="fb0e9-108">インクを収集するコントロールを作成するを参照してください。[インク入力コントロールの作成](creating-an-ink-input-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb0e9-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
