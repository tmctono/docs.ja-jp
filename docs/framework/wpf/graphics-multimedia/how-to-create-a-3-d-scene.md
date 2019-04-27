---
title: '方法: 3-D シーンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8e176cb437055787da86d56770dd71323134fa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910183"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="09f45-102">方法: 3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="09f45-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="09f45-103">この例では、回転紙のフラットなシートのような 3-D オブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09f45-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="09f45-104">A<xref:System.Windows.Controls.Viewport3D>次のコンポーネントと共にこのシンプルな 3-D シーンを作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="09f45-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="09f45-105">使用して、カメラを作成、<xref:System.Windows.Media.Media3D.PerspectiveCamera>します。</span><span class="sxs-lookup"><span data-stu-id="09f45-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="09f45-106">カメラでは、表示可能な 3-D シーンの部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="09f45-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="09f45-107">使用して 3-D オブジェクト (枚の用紙) の形状を指定するメッシュが作成、<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>プロパティの<xref:System.Windows.Media.Media3D.GeometryModel3D>します。</span><span class="sxs-lookup"><span data-stu-id="09f45-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="09f45-108">使用して、オブジェクト (このサンプルでの線形グラデーション) の表面に表示される素材が指定されて、<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>プロパティの<xref:System.Windows.Media.Media3D.GeometryModel3D>します。</span><span class="sxs-lookup"><span data-stu-id="09f45-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="09f45-109">オブジェクトを使用して、洗練するため、ライトが作成された<xref:System.Windows.Media.Media3D.DirectionalLight>します。</span><span class="sxs-lookup"><span data-stu-id="09f45-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09f45-110">例</span><span class="sxs-lookup"><span data-stu-id="09f45-110">Example</span></span>  
 <span data-ttu-id="09f45-111">次のコードでは、XAML で 3-D シーンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09f45-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="09f45-112">例</span><span class="sxs-lookup"><span data-stu-id="09f45-112">Example</span></span>  
 <span data-ttu-id="09f45-113">次のコードでは、手続き型コードで同じ 3-D シーンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09f45-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="09f45-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="09f45-114">See also</span></span>

- [<span data-ttu-id="09f45-115">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="09f45-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
