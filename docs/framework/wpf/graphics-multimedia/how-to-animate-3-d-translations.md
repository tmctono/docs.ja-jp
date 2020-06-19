---
title: '方法: 3D 翻訳をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112259"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="3e3ea-102">方法: 3D 翻訳をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3e3ea-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="3e3ea-103">このトピックでは、3D モデルで平行移動セットをアニメーション化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3ea-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="3e3ea-104">次のコードは、<xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> プロパティへの <xref:System.Windows.Media.Media3D.TranslateTransform3D> オブジェクトの適用を示しています。</span><span class="sxs-lookup"><span data-stu-id="3e3ea-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="3e3ea-105">この <xref:System.Windows.Media.Media3D.TranslateTransform3D> オブジェクトの <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> プロパティは、次のコードを使用してアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="3e3ea-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="3e3ea-106">例</span><span class="sxs-lookup"><span data-stu-id="3e3ea-106">Example</span></span>  
 <span data-ttu-id="3e3ea-107">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="3e3ea-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3e3ea-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e3ea-108">See also</span></span>

- [<span data-ttu-id="3e3ea-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="3e3ea-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3e3ea-110">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="3e3ea-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="3e3ea-111">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="3e3ea-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="3e3ea-112">変換の概要</span><span class="sxs-lookup"><span data-stu-id="3e3ea-112">Transforms Overview</span></span>](transforms-overview.md)
