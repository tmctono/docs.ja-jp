---
title: パスの作成および描画
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: a698b93aac29a0a7f5c959b29a3feb41eb447e8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935409"
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="26d4d-102">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="26d4d-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="26d4d-103">パスは、一連の操作し、1 つの単位として描画が可能なグラフィックス プリミティブ (線、四角形、曲線、テキスト、およびなど)。</span><span class="sxs-lookup"><span data-stu-id="26d4d-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="26d4d-104">パスを分割できる*図表*オープンかクローズのいずれかにあります。</span><span class="sxs-lookup"><span data-stu-id="26d4d-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="26d4d-105">図は、複数のプリミティブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="26d4d-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="26d4d-106">パスを描画するには呼び出すことによって、<xref:System.Drawing.Graphics.DrawPath%2A>のメソッド、<xref:System.Drawing.Graphics>クラス、およびを呼び出すことによってパスの塗りつぶしことができます、<xref:System.Drawing.Graphics.FillPath%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="26d4d-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26d4d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="26d4d-107">In This Section</span></span>  
 [<span data-ttu-id="26d4d-108">方法: 直線、曲線、および形状から図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="26d4d-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="26d4d-109">使用する方法を示しています、<xref:System.Drawing.Drawing2D.GraphicsPath>図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="26d4d-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="26d4d-110">方法: 開いている図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="26d4d-110">How to: Fill Open Figures</span></span>](how-to-fill-open-figures.md)  
 <span data-ttu-id="26d4d-111">入力する方法について説明します、<xref:System.Drawing.Drawing2D.GraphicsPath>します。</span><span class="sxs-lookup"><span data-stu-id="26d4d-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="26d4d-112">方法: 行に曲線のパスをフラット化します。</span><span class="sxs-lookup"><span data-stu-id="26d4d-112">How to: Flatten a Curved Path into a Line</span></span>](how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="26d4d-113">フラット化する方法を示しています、<xref:System.Drawing.Drawing2D.GraphicsPath>します。</span><span class="sxs-lookup"><span data-stu-id="26d4d-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="26d4d-114">参照</span><span class="sxs-lookup"><span data-stu-id="26d4d-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="26d4d-115">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26d4d-115">Describes this class and contains links to all of its members.</span></span>
