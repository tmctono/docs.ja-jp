---
title: '方法: インストールされたエンコーダーの一覧'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: ce297cb6d183bc63c8b276e30100aa4e864cd90d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078812"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="03445-102">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="03445-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="03445-103">アプリケーションが特定のイメージ ファイル形式に保存できるかどうかを確認するコンピューターでは、使用可能なイメージ エンコーダーの一覧を表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="03445-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="03445-104"><xref:System.Drawing.Imaging.ImageCodecInfo>クラスには、<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>静的メソッド イメージ エンコーダーが使用可能なを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="03445-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> <span data-ttu-id="03445-105">配列を返します<xref:System.Drawing.Imaging.ImageCodecInfo>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="03445-105">returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03445-106">例</span><span class="sxs-lookup"><span data-stu-id="03445-106">Example</span></span>  
 <span data-ttu-id="03445-107">次のコード例では、インストールされているエンコーダーの一覧とそのプロパティ値を出力します。</span><span class="sxs-lookup"><span data-stu-id="03445-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03445-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="03445-108">Compiling the Code</span></span>  
 <span data-ttu-id="03445-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03445-109">This example requires:</span></span>  
  
-   <span data-ttu-id="03445-110">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="03445-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="03445-111">A<xref:System.Windows.Forms.PaintEventArgs>はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="03445-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03445-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="03445-112">See also</span></span>

- [<span data-ttu-id="03445-113">方法: インストールされたデコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="03445-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="03445-114">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="03445-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
