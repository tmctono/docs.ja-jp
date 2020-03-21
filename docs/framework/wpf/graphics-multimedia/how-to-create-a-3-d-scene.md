---
title: '方法: 3D シーンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112103"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="64163-102">方法: 3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="64163-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="64163-103">次の例は、回転した平らな用紙のように見える 3D オブジェクトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64163-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="64163-104">この<xref:System.Windows.Controls.Viewport3D>シンプルな 3D シーンを作成するには、次のコンポーネントとともに A を使用します。</span><span class="sxs-lookup"><span data-stu-id="64163-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="64163-105">カメラは を使用して<xref:System.Windows.Media.Media3D.PerspectiveCamera>作成されます。</span><span class="sxs-lookup"><span data-stu-id="64163-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="64163-106">カメラは、3D シーンの表示可能な部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="64163-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="64163-107">のプロパティを使用して、3D オブジェクト (用紙シート) のシェイプを<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>指定する<xref:System.Windows.Media.Media3D.GeometryModel3D>メッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64163-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="64163-108">のプロパティを使用して、オブジェクトのサーフェスに表示されるマテリアル (このサンプルでは線形グラデーション)<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>を指定<xref:System.Windows.Media.Media3D.GeometryModel3D>します。</span><span class="sxs-lookup"><span data-stu-id="64163-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="64163-109">を使用してオブジェクトに光を当てる<xref:System.Windows.Media.Media3D.DirectionalLight>ライトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64163-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64163-110">例</span><span class="sxs-lookup"><span data-stu-id="64163-110">Example</span></span>  
 <span data-ttu-id="64163-111">次のコードは、XAML で 3D シーンを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64163-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="64163-112">例</span><span class="sxs-lookup"><span data-stu-id="64163-112">Example</span></span>  
 <span data-ttu-id="64163-113">以下のコードは、手続き型コードで同じ 3D シーンを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64163-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="64163-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="64163-114">See also</span></span>

- [<span data-ttu-id="64163-115">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="64163-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
