---
title: '方法: GroupBox テンプレートを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: dd53af87ec2d12b2ed0dcf2b23374d76e8f631a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225717"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="1e177-102">方法: GroupBox テンプレートを定義する</span><span class="sxs-lookup"><span data-stu-id="1e177-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="1e177-103">この例のテンプレートを作成する方法を示しています、<xref:System.Windows.Controls.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1e177-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e177-104">例</span><span class="sxs-lookup"><span data-stu-id="1e177-104">Example</span></span>  
 <span data-ttu-id="1e177-105">次の例では、定義、<xref:System.Windows.Controls.GroupBox>コントロール テンプレートを使用して、<xref:System.Windows.Controls.Grid>レイアウトを制御します。</span><span class="sxs-lookup"><span data-stu-id="1e177-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="1e177-106">テンプレートを使用して、<xref:System.Windows.Controls.BorderGapMaskConverter>の枠線を定義する、<xref:System.Windows.Controls.GroupBox>境界線が見えにくくならないように、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="1e177-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="1e177-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e177-107">See also</span></span>

- <xref:System.Windows.Controls.GroupBox>
- [<span data-ttu-id="1e177-108">方法: 作成 GroupBox</span><span class="sxs-lookup"><span data-stu-id="1e177-108">How to: Create a GroupBox</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
