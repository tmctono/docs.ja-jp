---
title: '方法: 自動レイアウト用のグリッドを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227133"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="c7fd1-102">方法: 自動レイアウト用のグリッドを使用する</span><span class="sxs-lookup"><span data-stu-id="c7fd1-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="c7fd1-103">この例では、自動レイアウトの方法でグリッドを使用して、ローカライズ可能なアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="c7fd1-104">ローカライズ、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="c7fd1-105">多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="c7fd1-106">過去の各言語を[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]が必要な調整を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="c7fd1-107">機能を今すぐ[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]調整の必要性が軽減される要素を設計することができます。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="c7fd1-108">簡単にサイズが変更および位置が変更された可能性のあるアプリケーションの作成方法と呼びます`auto layout`します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="c7fd1-109">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ボタンとテキストを配置するグリッドを使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="c7fd1-110">セルの幅と高さに設定されている通知`Auto`; イメージ付きのボタンを含むセルをそのため、イメージに合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="c7fd1-111"><xref:System.Windows.Controls.Grid>要素がローカライズされるアプリケーションの設計に自動レイアウトの方法を作成する際は、便利にすることができます、そのコンテンツを調整できます。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7fd1-112">例</span><span class="sxs-lookup"><span data-stu-id="c7fd1-112">Example</span></span>  
 <span data-ttu-id="c7fd1-113">次の例では、グリッドを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="c7fd1-114">次の図は、コード サンプルの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="c7fd1-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="c7fd1-115">![グリッドの例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="c7fd1-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="c7fd1-116">グリッド</span><span class="sxs-lookup"><span data-stu-id="c7fd1-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fd1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7fd1-117">See also</span></span>

- [<span data-ttu-id="c7fd1-118">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="c7fd1-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="c7fd1-119">自動レイアウトを使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="c7fd1-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
