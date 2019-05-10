---
title: '方法: エンコーダーがサポートするパラメーターの確認'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643335"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="f8ca8-102">方法: エンコーダーがサポートするパラメーターの確認</span><span class="sxs-lookup"><span data-stu-id="f8ca8-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="f8ca8-103">品質と圧縮レベルでなどの画像のパラメーターを調整することができますが、パラメーターが指定したイメージ エンコーダーでサポートされているを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="f8ca8-104"><xref:System.Drawing.Image>クラスには、<xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドどのイメージ パラメーターを特定のエンコーダーのサポートを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="f8ca8-105">GUID では、エンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="f8ca8-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドの配列を返します<xref:System.Drawing.Imaging.EncoderParameter>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ca8-107">例</span><span class="sxs-lookup"><span data-stu-id="f8ca8-107">Example</span></span>  
 <span data-ttu-id="f8ca8-108">次のコード例では、JPEG エンコーダーでサポートされているパラメーターを出力します。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="f8ca8-109">パラメーターのカテゴリと関連付けられている Guid のリストを使用して、<xref:System.Drawing.Imaging.Encoder>各パラメーターのカテゴリを確認するクラスの概要。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8ca8-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f8ca8-110">Compiling the Code</span></span>  
 <span data-ttu-id="f8ca8-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-111">This example requires:</span></span>  
  
- <span data-ttu-id="f8ca8-112">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f8ca8-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="f8ca8-113">A<xref:System.Windows.Forms.PaintEventArgs>はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="f8ca8-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ca8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8ca8-114">See also</span></span>

- [<span data-ttu-id="f8ca8-115">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="f8ca8-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="f8ca8-116">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="f8ca8-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="f8ca8-117">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="f8ca8-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
