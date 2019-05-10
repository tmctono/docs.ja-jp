---
title: グラフィックスについて
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: 927fc327d9ad42cd3a99af207d04efbc520df8b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645700"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="2af02-102">グラフィックスについて</span><span class="sxs-lookup"><span data-stu-id="2af02-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2af02-103">Microsoft Windows オペレーティング システムのサブシステムを形成するアプリケーション プログラミング インターフェイス (API) です。</span><span class="sxs-lookup"><span data-stu-id="2af02-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2af02-104">情報を表示する画面およびプリンターを担当します。</span><span class="sxs-lookup"><span data-stu-id="2af02-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="2af02-105">その名前からわかるように、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] は [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] の後継であり、以前のバージョンの Windows に含まれているグラフィックス デバイス インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2af02-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="2af02-106">マネージド クラスのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2af02-106">Managed Class Interface</span></span>  
 <span data-ttu-id="2af02-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API はマネージ コードとして配置されているクラスのセットを通じて公開します。</span><span class="sxs-lookup"><span data-stu-id="2af02-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="2af02-108">このクラスのセットと呼ばれる、*マネージ クラスのインターフェイス*に[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2af02-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="2af02-109">次の名前空間は、マネージド クラスのインターフェイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2af02-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="2af02-110">グラフィックス デバイス インターフェイスを備えたなど[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、画面またはプリンターの情報を表示するには、特定のディスプレイ デバイスの詳細について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2af02-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="2af02-111">プログラマは [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] クラスによって提供されるさまざまなメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2af02-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="2af02-112">次に、これらのメソッドで、特定のデバイス ドライバーへの適切な呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="2af02-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2af02-113">は、グラフィックス ハードウェアからアプリケーションを分離します。</span><span class="sxs-lookup"><span data-stu-id="2af02-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="2af02-114">この分離により、プログラマはデバイスに依存しないアプリケーションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2af02-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af02-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2af02-115">See also</span></span>

- [<span data-ttu-id="2af02-116">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="2af02-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
