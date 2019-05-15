---
title: 複雑なグリッドを作成する方法
description: グリッド コントロールを使用して、月間予定表のようなレイアウトを作成する方法の例です。
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: ab5490d608b21fe8b29a078dc1f0147f038c27a3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645670"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="db7bd-103">複雑なグリッドを作成する方法</span><span class="sxs-lookup"><span data-stu-id="db7bd-103">How to create a complex Grid</span></span>

<span data-ttu-id="db7bd-104">この例は、使用する方法を示します、<xref:System.Windows.Controls.Grid>月間予定表のようなレイアウトを作成するコントロール。</span><span class="sxs-lookup"><span data-stu-id="db7bd-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="db7bd-105">例</span><span class="sxs-lookup"><span data-stu-id="db7bd-105">Example</span></span>

<span data-ttu-id="db7bd-106">次の例を使用して 8 つの行と 8 つの列の定義、<xref:System.Windows.Controls.RowDefinition>と<xref:System.Windows.Controls.ColumnDefinition>クラス。</span><span class="sxs-lookup"><span data-stu-id="db7bd-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="db7bd-107">使用して、<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>と<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>と共に添付プロパティ、<xref:System.Windows.Shapes.Rectangle>要素で、さまざまな列と行の背景色を入力します。</span><span class="sxs-lookup"><span data-stu-id="db7bd-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="db7bd-108">この設計は、の各セルには、複数の要素が存在できますので、可能な<xref:System.Windows.Controls.Grid>、原則違い<xref:System.Windows.Controls.Grid>と<xref:System.Windows.Documents.Table>。</span><span class="sxs-lookup"><span data-stu-id="db7bd-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="db7bd-109">例では、使用する垂直方向のグラデーション<xref:System.Windows.Shapes.Shape.Fill%2A>列とビジュアルのプレゼンテーションや予定表の読みやすさを向上させるために行。</span><span class="sxs-lookup"><span data-stu-id="db7bd-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="db7bd-110">スタイル<xref:System.Windows.Controls.TextBlock>要素は、日付と曜日を表します。</span><span class="sxs-lookup"><span data-stu-id="db7bd-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="db7bd-111"><xref:System.Windows.Controls.TextBlock> 要素は、セル内を使用して絶対位置、<xref:System.Windows.FrameworkElement.Margin%2A>プロパティと配置プロパティ、アプリケーションのスタイル内で定義されています。</span><span class="sxs-lookup"><span data-stu-id="db7bd-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="db7bd-112">次の図は、生成されたコントロール、カスタマイズ可能なカレンダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="db7bd-112">The following image shows the resulting control, a customizable calendar:</span></span>

![生成されたコントロールのスクリーン ショット](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="db7bd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="db7bd-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="db7bd-115">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="db7bd-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="db7bd-116">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="db7bd-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="db7bd-117">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="db7bd-117">Table Overview</span></span>](../advanced/table-overview.md)
