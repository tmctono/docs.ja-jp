---
title: '方法: 要素およびコントロールのマージンを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052366"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="0fc29-102">方法: 要素およびコントロールのマージンを設定する</span><span class="sxs-lookup"><span data-stu-id="0fc29-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="0fc29-103">この例の説明を設定する方法、<xref:System.Windows.FrameworkElement.Margin%2A>分離コードで余白の幅を既存のプロパティ値を変更することで、プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0fc29-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="0fc29-104"><xref:System.Windows.FrameworkElement.Margin%2A>プロパティのプロパティである、<xref:System.Windows.FrameworkElement>要素の基本し、さまざまなコントロールとその他の要素によって継承されるためです。</span><span class="sxs-lookup"><span data-stu-id="0fc29-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="0fc29-105">この例で記述された[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、分離コード ファイルを[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を参照します。</span><span class="sxs-lookup"><span data-stu-id="0fc29-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="0fc29-106">両方の分離コードが示すように、C#と Microsoft Visual Basic バージョン。</span><span class="sxs-lookup"><span data-stu-id="0fc29-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fc29-107">例</span><span class="sxs-lookup"><span data-stu-id="0fc29-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
