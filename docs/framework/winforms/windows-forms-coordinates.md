---
title: Windows フォームの座標
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: 6feabadff17538f4a7368c348f7b72226e2d678e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980656"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="bfebc-102">Windows フォームの座標</span><span class="sxs-lookup"><span data-stu-id="bfebc-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="bfebc-103">Windows フォームの座標システムは、デバイス座標に基づいており、Windows フォームで描画するときに、メジャーの基本単位はデバイス単位 (通常は、ピクセル) です。</span><span class="sxs-lookup"><span data-stu-id="bfebc-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="bfebc-104">画面上の点は、増加、右、上から下に増やすと、y 座標の x 座標と、x 座標と y 座標のペアで説明します。</span><span class="sxs-lookup"><span data-stu-id="bfebc-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="bfebc-105">画面を基準とした、元の場所は、画面またはクライアント座標を指定するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bfebc-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="bfebc-106">画面座標</span><span class="sxs-lookup"><span data-stu-id="bfebc-106">Screen Coordinates</span></span>  
 <span data-ttu-id="bfebc-107">Windows フォーム アプリケーションでは、画面座標では、画面上のウィンドウの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfebc-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="bfebc-108">画面座標の原点は、画面の左上隅です。</span><span class="sxs-lookup"><span data-stu-id="bfebc-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="bfebc-109">ウィンドウの完全な位置がによって定義された多くの場合、<xref:System.Drawing.Rectangle>ウィンドウの左上隅および右の角を定義する 2 つの点の画面座標を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="bfebc-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="bfebc-110">クライアント座標</span><span class="sxs-lookup"><span data-stu-id="bfebc-110">Client Coordinates</span></span>  
 <span data-ttu-id="bfebc-111">Windows フォーム アプリケーションでは、フォームまたはコントロールのクライアント座標を使用してポイントの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfebc-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="bfebc-112">クライアント座標の原点は、コントロールまたはフォームのクライアント領域の左上隅です。</span><span class="sxs-lookup"><span data-stu-id="bfebc-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="bfebc-113">クライアント座標では、アプリケーションがフォームまたはフォームまたは画面上のコントロールの位置に関係なく、コントロールの描画中に一貫性のある座標値を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfebc-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="bfebc-114">クライアント領域のディメンションがによって記述も、<xref:System.Drawing.Rectangle>領域のクライアント座標を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="bfebc-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="bfebc-115">どの場合も、右下の座標が除外されているときに、クライアント領域に四角形の左上隅の座標が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfebc-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="bfebc-116">グラフィックスの操作は、クライアント領域の右および下端を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="bfebc-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="bfebc-117">たとえば、<xref:System.Drawing.Graphics.FillRectangle%2A>メソッドは、指定した四角形の右方向と下の端にいっぱいになりますが、これらのエッジは含まれません。</span><span class="sxs-lookup"><span data-stu-id="bfebc-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="bfebc-118">座標の 1 つの型から別のマッピング</span><span class="sxs-lookup"><span data-stu-id="bfebc-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="bfebc-119">場合によっては、画面座標からクライアント座標にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfebc-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="bfebc-120">簡単にこれを使用して、<xref:System.Windows.Forms.Control.PointToClient%2A>と<xref:System.Windows.Forms.Control.PointToScreen%2A>メソッドで使用できる、<xref:System.Windows.Forms.Control>クラス。</span><span class="sxs-lookup"><span data-stu-id="bfebc-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="bfebc-121">たとえば、<xref:System.Windows.Forms.Control.MousePosition%2A>プロパティの<xref:System.Windows.Forms.Control>画面座標で報告されたクライアント座標に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="bfebc-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfebc-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfebc-122">See also</span></span>

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
