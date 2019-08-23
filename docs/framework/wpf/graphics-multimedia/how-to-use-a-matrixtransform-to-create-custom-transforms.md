---
title: '方法: MatrixTransform を使用してカスタム変換を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913917"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="837bf-102">方法: MatrixTransform を使用してカスタム変換を作成する</span><span class="sxs-lookup"><span data-stu-id="837bf-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="837bf-103">この例で<xref:System.Windows.Media.MatrixTransform>は、を使用して、 <xref:System.Windows.Controls.Button>の位置、伸縮、および傾斜を変換 (移動) する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="837bf-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="837bf-104"><xref:System.Windows.Media.SkewTransform> <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.TranslateTransform>クラスを使用して、、 <xref:System.Windows.Media.ScaleTransform>、、またはの各クラスで提供されないカスタム変換を作成します。 <xref:System.Windows.Media.MatrixTransform></span><span class="sxs-lookup"><span data-stu-id="837bf-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="837bf-105">例</span><span class="sxs-lookup"><span data-stu-id="837bf-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="837bf-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="837bf-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="837bf-107">変換の概要</span><span class="sxs-lookup"><span data-stu-id="837bf-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="837bf-108">方法トピック</span><span class="sxs-lookup"><span data-stu-id="837bf-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="837bf-109">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="837bf-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
