---
title: グラフィックス コンテナーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704474"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="76f92-102">グラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="76f92-102">Using Graphics Containers</span></span>
<span data-ttu-id="76f92-103">A<xref:System.Drawing.Graphics>オブジェクトなどのメソッドを提供<xref:System.Drawing.Graphics.DrawLine%2A>、 <xref:System.Drawing.Graphics.DrawImage%2A>、および<xref:System.Drawing.Graphics.DrawString%2A>ベクター イメージ、ラスター イメージ、およびテキストを表示するためです。</span><span class="sxs-lookup"><span data-stu-id="76f92-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="76f92-104">A<xref:System.Drawing.Graphics>オブジェクトにも、品質とは、描画される項目の向きに影響を与えるいくつかのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="76f92-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="76f92-105">たとえば、スムージング モード プロパティは、線と曲線にアンチエイリアシングを適用し、位置と回転は、描画される項目のワールド変換プロパティに影響を与えますかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="76f92-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="76f92-106">A<xref:System.Drawing.Graphics>オブジェクトが特定のディスプレイ デバイスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="76f92-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="76f92-107">使用すると、<xref:System.Drawing.Graphics>ウィンドウで、描画するオブジェクト、<xref:System.Drawing.Graphics>オブジェクトは、その特定のウィンドウに関連付けられてもします。</span><span class="sxs-lookup"><span data-stu-id="76f92-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="76f92-108">A<xref:System.Drawing.Graphics>オブジェクトはコンテナーとして描画に影響を与えるプロパティのセットを保持していると、デバイスに固有の情報にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="76f92-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="76f92-109">内で、既存のセカンダリのコンテナーを作成する<xref:System.Drawing.Graphics>オブジェクトを呼び出すことによって、<xref:System.Drawing.Graphics.BeginContainer%2A>メソッドの<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="76f92-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76f92-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="76f92-110">In This Section</span></span>  
 [<span data-ttu-id="76f92-111">Graphics オブジェクトの状態の管理</span><span class="sxs-lookup"><span data-stu-id="76f92-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="76f92-112">について説明します、品質の設定、クリッピング領域との変換を管理する方法、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="76f92-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="76f92-113">入れ子になっているグラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="76f92-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="76f92-114">コンテナーを使用しての状態を制御する方法を示しています、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="76f92-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
