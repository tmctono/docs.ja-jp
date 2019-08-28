---
title: '方法: RichTextBox コントロール上にドロップしたファイルを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046352"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="e104a-102">方法: RichTextBox コントロール上にドロップしたファイルを開く</span><span class="sxs-lookup"><span data-stu-id="e104a-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>

<span data-ttu-id="e104a-103">で[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]は、 <xref:System.Windows.Controls.TextBox>、 <xref:System.Windows.Controls.RichTextBox>、および<xref:System.Windows.Documents.FlowDocument>の各コントロールには、ドラッグアンドドロップ機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="e104a-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="e104a-104">組み込み機能を使用すると、コントロール内およびコントロール間でテキストをドラッグアンドドロップできます。</span><span class="sxs-lookup"><span data-stu-id="e104a-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="e104a-105">ただし、コントロール上のファイルを削除することによってファイルを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="e104a-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="e104a-106">また、これらのコントロールは、ドラッグアンドドロップイベントを処理済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="e104a-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="e104a-107">その結果、既定では、削除されたファイルを開く機能を提供するための独自のイベントハンドラーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="e104a-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>

<span data-ttu-id="e104a-108">これらのコントロールでドラッグアンドドロップイベントの処理を追加するには、 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>メソッドを使用して、ドラッグアンドドロップイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e104a-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="e104a-109">イベントルート`handledEventsToo`上の`true`別の要素によって既に処理済みとしてマークされているルーティングイベントに対して、指定したハンドラーが呼び出されるようにするには、パラメーターをに設定します。</span><span class="sxs-lookup"><span data-stu-id="e104a-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>

> [!TIP]
> <span data-ttu-id="e104a-110">ドラッグアンドドロップイベントのプレビューバージョンを処理し、プレビューイベントを<xref:System.Windows.Controls.TextBox>処理<xref:System.Windows.Controls.RichTextBox>済みと<xref:System.Windows.Documents.FlowDocument>してマークすることによって、、、の組み込みのドラッグアンドドロップ機能を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="e104a-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="e104a-111">ただし、これにより、組み込みのドラッグアンドドロップ機能が無効になるため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="e104a-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>

## <a name="example"></a><span data-ttu-id="e104a-112">例</span><span class="sxs-lookup"><span data-stu-id="e104a-112">Example</span></span>

<span data-ttu-id="e104a-113">次の例は、に<xref:System.Windows.DragDrop.DragOver> <xref:System.Windows.Controls.RichTextBox>イベントと<xref:System.Windows.DragDrop.Drop>イベントのハンドラーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e104a-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="e104a-114">この例では<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 、メソッドを使用`handledEventsToo`し、 `true`パラメーターをに設定して、がこれらのイベント<xref:System.Windows.Controls.RichTextBox>を処理済みとしてマークしている場合でも、イベントハンドラーが呼び出されるようにします。</span><span class="sxs-lookup"><span data-stu-id="e104a-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="e104a-115">イベントハンドラーのコードは、 <xref:System.Windows.Controls.RichTextBox>にドロップされたテキストファイルを開くための機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="e104a-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>

<span data-ttu-id="e104a-116">この例をテストするには、Windows エクスプローラーからに<xref:System.Windows.Controls.RichTextBox>テキストファイルまたはリッチテキスト形式 (RTF) ファイルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e104a-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="e104a-117">ファイルはで<xref:System.Windows.Controls.RichTextBox>開かれます。</span><span class="sxs-lookup"><span data-stu-id="e104a-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="e104a-118">ファイルを削除する前に SHIFT キーを押すと、ファイルはプレーンテキストとして開かれます。</span><span class="sxs-lookup"><span data-stu-id="e104a-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
