---
title: '方法: 自動レイアウトを使用してボタンを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 8eb1e93dd87c210812c9b7758c744a616ef2d862
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052392"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="4d723-102">方法: 自動レイアウトを使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="4d723-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="4d723-103">この例では、自動レイアウトの方法を使用して、ローカライズ可能なアプリケーションにボタンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d723-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="4d723-104">ローカライズ、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="4d723-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="4d723-105">多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d723-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="4d723-106">過去の各言語を[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]が必要な調整を変更します。</span><span class="sxs-lookup"><span data-stu-id="4d723-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="4d723-107">機能を今すぐ[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]調整の必要性が軽減される要素を設計することができます。</span><span class="sxs-lookup"><span data-stu-id="4d723-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="4d723-108">簡単にサイズ変更や位置が変更された可能性のあるアプリケーションの作成方法と呼びます`automatic layout`します。</span><span class="sxs-lookup"><span data-stu-id="4d723-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d723-109">例</span><span class="sxs-lookup"><span data-stu-id="4d723-109">Example</span></span>  

<span data-ttu-id="4d723-110">次の 2 つ[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の例は、ボタン; スペイン語のテキストのいずれかと英語のテキストを 1 つのインスタンスを作成するアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d723-110">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="4d723-111">テキストを除き、コードは同じであることに注目してください。ボタンがテキストに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="4d723-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="4d723-112">次の図は、自動サイズ変更可能なボタンのコード サンプルの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d723-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![テキストの言語が異なる同じボタン](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="4d723-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d723-114">See also</span></span>

- [<span data-ttu-id="4d723-115">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="4d723-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="4d723-116">自動レイアウト用のグリッドを使用する</span><span class="sxs-lookup"><span data-stu-id="4d723-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
