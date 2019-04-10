---
title: '方法: MatrixTransform を使用してカスタム変換を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182313"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="9f6fa-102">方法: MatrixTransform を使用してカスタム変換を作成する</span><span class="sxs-lookup"><span data-stu-id="9f6fa-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="9f6fa-103">この例は、使用する方法を示します、<xref:System.Windows.Media.MatrixTransform>変換 (移動) する位置を stretch との差を<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="9f6fa-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f6fa-104">使用、<xref:System.Windows.Media.MatrixTransform>によって提供されないカスタム変換を作成するクラス、 <xref:System.Windows.Media.RotateTransform>、 <xref:System.Windows.Media.SkewTransform>、 <xref:System.Windows.Media.ScaleTransform>、または<xref:System.Windows.Media.TranslateTransform>のクラス。</span><span class="sxs-lookup"><span data-stu-id="9f6fa-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f6fa-105">例</span><span class="sxs-lookup"><span data-stu-id="9f6fa-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="9f6fa-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f6fa-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="9f6fa-107">変換の概要</span><span class="sxs-lookup"><span data-stu-id="9f6fa-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="9f6fa-108">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="9f6fa-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="9f6fa-109">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="9f6fa-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
