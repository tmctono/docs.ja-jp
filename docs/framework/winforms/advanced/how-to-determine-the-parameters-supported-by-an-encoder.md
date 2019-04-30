---
title: '方法: エンコーダーがサポートするパラメーターの確認'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004329"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="9c945-102">方法: エンコーダーがサポートするパラメーターの確認</span><span class="sxs-lookup"><span data-stu-id="9c945-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="9c945-103">品質と圧縮レベルでなどの画像のパラメーターを調整することができますが、パラメーターが指定したイメージ エンコーダーでサポートされているを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c945-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="9c945-104"><xref:System.Drawing.Image>クラスには、<xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドどのイメージ パラメーターを特定のエンコーダーのサポートを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9c945-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="9c945-105">GUID では、エンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c945-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="9c945-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A>メソッドの配列を返します<xref:System.Drawing.Imaging.EncoderParameter>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9c945-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c945-107">例</span><span class="sxs-lookup"><span data-stu-id="9c945-107">Example</span></span>  
 <span data-ttu-id="9c945-108">次のコード例では、JPEG エンコーダーでサポートされているパラメーターを出力します。</span><span class="sxs-lookup"><span data-stu-id="9c945-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="9c945-109">パラメーターのカテゴリと関連付けられている Guid のリストを使用して、<xref:System.Drawing.Imaging.Encoder>各パラメーターのカテゴリを確認するクラスの概要。</span><span class="sxs-lookup"><span data-stu-id="9c945-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c945-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9c945-110">Compiling the Code</span></span>  
 <span data-ttu-id="9c945-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c945-111">This example requires:</span></span>  
  
- <span data-ttu-id="9c945-112">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9c945-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="9c945-113">A<xref:System.Windows.Forms.PaintEventArgs>はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="9c945-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c945-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c945-114">See also</span></span>

- [<span data-ttu-id="9c945-115">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="9c945-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="9c945-116">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="9c945-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="9c945-117">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="9c945-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
