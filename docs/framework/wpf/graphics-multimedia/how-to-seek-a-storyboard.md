---
title: '方法: ストーリーボードをシークする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: a57272c17a5bc6f5baaa21fb77233fc5693d1914
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131665"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="ad69e-102">方法: ストーリーボードをシークする</span><span class="sxs-lookup"><span data-stu-id="ad69e-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="ad69e-103">次の例は、使用する方法を示します、<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>のメソッド、<xref:System.Windows.Media.Animation.Storyboard>ストーリー ボード アニメーションの任意の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad69e-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad69e-104">例</span><span class="sxs-lookup"><span data-stu-id="ad69e-104">Example</span></span>  
 <span data-ttu-id="ad69e-105">サンプルの XAML マークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad69e-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="ad69e-106">例</span><span class="sxs-lookup"><span data-stu-id="ad69e-106">Example</span></span>  
 <span data-ttu-id="ad69e-107">上記の XAML コードと共に使用するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad69e-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ad69e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad69e-108">See also</span></span>

- [<span data-ttu-id="ad69e-109">ストーリーボードを同期的にシークする</span><span class="sxs-lookup"><span data-stu-id="ad69e-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
