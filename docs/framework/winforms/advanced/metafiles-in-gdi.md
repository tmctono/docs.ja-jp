---
title: GDI+ でのメタファイル
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504593"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="9cd33-102">GDI+ でのメタファイル</span><span class="sxs-lookup"><span data-stu-id="9cd33-102">Metafiles in GDI+</span></span>
<span data-ttu-id="9cd33-103">GDI + は、提供、<xref:System.Drawing.Imaging.Metafile>クラスに記録し、メタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="9cd33-104">ベクター イメージとも呼ばれる、メタファイルは、一連の描画コマンドと設定として格納されているイメージです。</span><span class="sxs-lookup"><span data-stu-id="9cd33-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="9cd33-105">コマンドおよび設定に記録する<xref:System.Drawing.Imaging.Metafile>オブジェクトをメモリに格納されているか、ファイルまたはストリームに保存します。</span><span class="sxs-lookup"><span data-stu-id="9cd33-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="9cd33-106">メタファイル形式</span><span class="sxs-lookup"><span data-stu-id="9cd33-106">Metafile Formats</span></span>  
 <span data-ttu-id="9cd33-107">GDI + は、次の形式で格納されているメタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="9cd33-108">Windows メタファイル (WMF)</span><span class="sxs-lookup"><span data-stu-id="9cd33-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="9cd33-109">拡張メタファイル (EMF)</span><span class="sxs-lookup"><span data-stu-id="9cd33-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="9cd33-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="9cd33-110">EMF+</span></span>  
  
 <span data-ttu-id="9cd33-111">GDI + を記録できますメタファイル WMF 形式ではなく、EMF、EMF + 形式にします。</span><span class="sxs-lookup"><span data-stu-id="9cd33-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="9cd33-112">EMF + GDI + レコードを格納することができる EMF の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="9cd33-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="9cd33-113">EMF + 形式の 2 つのバリエーションがあります。EMF + のみと EMF + Dual します。</span><span class="sxs-lookup"><span data-stu-id="9cd33-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="9cd33-114">メタファイル EMF + だけでは、GDI + レコードだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="9cd33-115">GDI + では、GDI ではなく、このようなメタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="9cd33-116">EMF + Dual メタファイルには、GDI + と GDI レコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="9cd33-117">EMF + Dual メタファイルに各の GDI + レコードは、代替 GDI レコードと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="9cd33-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="9cd33-118">このようなメタファイルは、GDI または GDI + によって表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cd33-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="9cd33-119">次の例では、ファイルとして保存された以前メタファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd33-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="9cd33-120">左上隅にあるとメタファイルが表示されます (100, 100)。</span><span class="sxs-lookup"><span data-stu-id="9cd33-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="9cd33-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cd33-121">See also</span></span>

- [<span data-ttu-id="9cd33-122">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="9cd33-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
