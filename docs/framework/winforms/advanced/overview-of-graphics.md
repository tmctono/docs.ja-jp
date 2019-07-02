---
title: グラフィックスについて
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505324"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="37ce3-102">グラフィックスについて</span><span class="sxs-lookup"><span data-stu-id="37ce3-102">Overview of Graphics</span></span>
<span data-ttu-id="37ce3-103">GDI + は、Microsoft Windows オペレーティング システムのサブシステムを形成するアプリケーション プログラミング インターフェイス (API です)。</span><span class="sxs-lookup"><span data-stu-id="37ce3-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="37ce3-104">GDI + は画面およびプリンター情報を表示する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="37ce3-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="37ce3-105">その名前からわかるように、GDI + は GDI、以前のバージョンの Windows に含まれているグラフィックス デバイス インターフェイスの後継です。</span><span class="sxs-lookup"><span data-stu-id="37ce3-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="37ce3-106">マネージド クラスのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="37ce3-106">Managed Class Interface</span></span>  
 <span data-ttu-id="37ce3-107">GDI + API は、マネージ コードとして配置されているクラスのセットを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="37ce3-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="37ce3-108">この一連のクラスと呼ばれる、*マネージ クラスのインターフェイス*GDI + にします。</span><span class="sxs-lookup"><span data-stu-id="37ce3-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="37ce3-109">次の名前空間は、マネージド クラスのインターフェイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="37ce3-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="37ce3-110">GDI + などのグラフィックス デバイス インターフェイスを持つ特定のディスプレイ デバイスの詳細について心配することがなく、画面またはプリンターの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="37ce3-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="37ce3-111">プログラマでは、GDI + クラスによって提供されるメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="37ce3-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="37ce3-112">次に、これらのメソッドで、特定のデバイス ドライバーへの適切な呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="37ce3-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="37ce3-113">GDI +、グラフィックス ハードウェアからアプリケーションを隔離します。</span><span class="sxs-lookup"><span data-stu-id="37ce3-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="37ce3-114">この分離により、プログラマはデバイスに依存しないアプリケーションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37ce3-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ce3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ce3-115">See also</span></span>

- [<span data-ttu-id="37ce3-116">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="37ce3-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
