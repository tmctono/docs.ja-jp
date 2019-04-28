---
title: '方法: プログラムによってコンテンツの FlowDirection を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776559"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="e8bd6-102">方法: プログラムによってコンテンツの FlowDirection を変更する</span><span class="sxs-lookup"><span data-stu-id="e8bd6-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="e8bd6-103">この例は、プログラムで変更する方法を示します、<xref:System.Windows.FrameworkElement.FlowDirection%2A>のプロパティを<xref:System.Windows.Controls.FlowDocumentReader>します。</span><span class="sxs-lookup"><span data-stu-id="e8bd6-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8bd6-104">例</span><span class="sxs-lookup"><span data-stu-id="e8bd6-104">Example</span></span>  
 <span data-ttu-id="e8bd6-105">2 つ<xref:System.Windows.Controls.Button>要素が作成可能な値のいずれかを表す各<xref:System.Windows.FlowDirection>します。</span><span class="sxs-lookup"><span data-stu-id="e8bd6-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="e8bd6-106">内容に関連付けられているプロパティ値を適用するボタンがクリックされたときに、<xref:System.Windows.Controls.FlowDocumentReader>という`tf1`します。</span><span class="sxs-lookup"><span data-stu-id="e8bd6-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="e8bd6-107">プロパティの値に書き込まれます、<xref:System.Windows.Controls.TextBlock>という`txt1`します。</span><span class="sxs-lookup"><span data-stu-id="e8bd6-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="e8bd6-108">例</span><span class="sxs-lookup"><span data-stu-id="e8bd6-108">Example</span></span>  
 <span data-ttu-id="e8bd6-109">上記で定義されたボタンのクリックに関連付けられているイベントで処理をC#分離コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="e8bd6-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
