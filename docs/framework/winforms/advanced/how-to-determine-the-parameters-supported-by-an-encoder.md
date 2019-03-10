---
title: '方法: エンコーダーがサポートするパラメーターを確認します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: f5af00833c8d8373444b475673709d902598d9d0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719703"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="ada65-102">方法: エンコーダーがサポートするパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="ada65-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="ada65-103">品質と圧縮レベルでなどの画像のパラメーターを調整することができますが、パラメーターが指定したイメージ エンコーダーでサポートされているを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada65-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="ada65-104"><xref:System.Drawing.Image>クラスには、<xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドどのイメージ パラメーターを特定のエンコーダーのサポートを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ada65-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="ada65-105">GUID では、エンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ada65-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="ada65-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドの配列を返します<xref:System.Drawing.Imaging.EncoderParameter>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ada65-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada65-107">例</span><span class="sxs-lookup"><span data-stu-id="ada65-107">Example</span></span>  
 <span data-ttu-id="ada65-108">次のコード例では、JPEG エンコーダーでサポートされているパラメーターを出力します。</span><span class="sxs-lookup"><span data-stu-id="ada65-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="ada65-109">パラメーターのカテゴリと関連付けられている Guid のリストを使用して、<xref:System.Drawing.Imaging.Encoder>各パラメーターのカテゴリを確認するクラスの概要。</span><span class="sxs-lookup"><span data-stu-id="ada65-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ada65-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ada65-110">Compiling the Code</span></span>  
 <span data-ttu-id="ada65-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ada65-111">This example requires:</span></span>  
  
-   <span data-ttu-id="ada65-112">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ada65-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="ada65-113">A<xref:System.Windows.Forms.PaintEventArgs>はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="ada65-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada65-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ada65-114">See also</span></span>
- [<span data-ttu-id="ada65-115">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="ada65-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="ada65-116">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="ada65-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="ada65-117">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="ada65-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
