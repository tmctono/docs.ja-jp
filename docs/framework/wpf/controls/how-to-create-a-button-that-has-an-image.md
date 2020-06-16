---
title: '方法: イメージを持つ Button を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910950"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="6057c-102">方法: イメージを持つ Button を作成する</span><span class="sxs-lookup"><span data-stu-id="6057c-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="6057c-103">この例では、<xref:System.Windows.Controls.Button> でイメージを含める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6057c-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6057c-104">例</span><span class="sxs-lookup"><span data-stu-id="6057c-104">Example</span></span>  
 <span data-ttu-id="6057c-105">次の例では、2 つの <xref:System.Windows.Controls.Button> コントロールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6057c-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="6057c-106">一方の <xref:System.Windows.Controls.Button> にはテキストが含まれ、もう一方にはイメージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6057c-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="6057c-107">イメージはデータという名称のフォルダーに入ります。このフォルダーは、例のプロジェクト フォルダーのサブフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6057c-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="6057c-108">イメージが含まれる <xref:System.Windows.Controls.Button> をユーザーがクリックすると、他の <xref:System.Windows.Controls.Button> の背景とテキストが変わります。</span><span class="sxs-lookup"><span data-stu-id="6057c-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="6057c-109">この例では、マークアップを利用して <xref:System.Windows.Controls.Button> コントロールが作成されますが、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーの記述にはコードが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6057c-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6057c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6057c-110">See also</span></span>

- [<span data-ttu-id="6057c-111">コントロール</span><span class="sxs-lookup"><span data-stu-id="6057c-111">Controls</span></span>](index.md)
- [<span data-ttu-id="6057c-112">コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="6057c-112">Control Library</span></span>](control-library.md)
