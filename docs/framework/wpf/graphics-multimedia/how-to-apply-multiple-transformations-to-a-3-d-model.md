---
title: '方法: 3D モデルに複数の変換を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 6400d224fb51b93c76c5e9798b4bcc68ff3b9de6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112129"
---
# <a name="how-to-apply-multiple-transformations-to-a-3d-model"></a><span data-ttu-id="4288f-102">方法: 3D モデルに複数の変換を適用する</span><span class="sxs-lookup"><span data-stu-id="4288f-102">How to: Apply Multiple Transformations to a 3D Model</span></span>
<span data-ttu-id="4288f-103">このサンプルでは、a<xref:System.Windows.Media.Media3D.RotateTransform3D>および a<xref:System.Windows.Media.Media3D.ScaleTransform3D>を使用して 3D モデルのスケールを回転および変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4288f-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3D model.</span></span> <span data-ttu-id="4288f-104">次のコードは、XAML のプロパティにこれらの変換<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>を適用する<xref:System.Windows.Media.Media3D.GeometryModel3D>方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4288f-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="4288f-105">コード内で以下のように指定します。</span><span class="sxs-lookup"><span data-stu-id="4288f-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="4288f-106">例</span><span class="sxs-lookup"><span data-stu-id="4288f-106">Example</span></span>  
 <span data-ttu-id="4288f-107">次のコードは、XAML のサンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="4288f-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4288f-108">例</span><span class="sxs-lookup"><span data-stu-id="4288f-108">Example</span></span>  
 <span data-ttu-id="4288f-109">以下はコードのサンプル全体です。</span><span class="sxs-lookup"><span data-stu-id="4288f-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4288f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4288f-110">See also</span></span>

- [<span data-ttu-id="4288f-111">3D モデルのスケールを変換する</span><span class="sxs-lookup"><span data-stu-id="4288f-111">Transform the Scale of a 3D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
