---
title: '方法: 3-D 変換をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 0290beac5a92a955b39d0b8fcc24705346c2964a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351919"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="96f82-102">方法: 3-D 変換をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="96f82-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="96f82-103">このトピックでは、移動変換をアニメーション化する方法を示します、[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]モデル。</span><span class="sxs-lookup"><span data-stu-id="96f82-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="96f82-104">次のコードのアプリケーションを示しています、<xref:System.Windows.Media.Media3D.TranslateTransform3D>オブジェクトを<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>のプロパティを<xref:System.Windows.Media.Media3D.GeometryModel3D>します。</span><span class="sxs-lookup"><span data-stu-id="96f82-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="96f82-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A>プロパティのこの<xref:System.Windows.Media.Media3D.TranslateTransform3D>オブジェクトは次のコードを使用してアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="96f82-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="96f82-106">例</span><span class="sxs-lookup"><span data-stu-id="96f82-106">Example</span></span>  
 <span data-ttu-id="96f82-107">次のコードでは、全体のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="96f82-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="96f82-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="96f82-108">See also</span></span>
- [<span data-ttu-id="96f82-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="96f82-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="96f82-110">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="96f82-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="96f82-111">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="96f82-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="96f82-112">変換の概要</span><span class="sxs-lookup"><span data-stu-id="96f82-112">Transforms Overview</span></span>](transforms-overview.md)
