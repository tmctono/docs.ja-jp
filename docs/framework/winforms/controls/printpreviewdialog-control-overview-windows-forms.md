---
title: PrintPreviewDialog コントロールの概要
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741416"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="99af8-102">Printプレビューダイアログコントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="99af8-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="99af8-103">Windows フォーム <xref:System.Windows.Forms.PrintPreviewDialog> コントロールは、印刷時に[PrintDocument](printdocument-component-windows-forms.md)がどのように表示されるかを表示するために事前に構成されたダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="99af8-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="99af8-104">独自のダイアログボックスを構成するのではなく、単純なソリューションとして Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="99af8-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="99af8-105">このコントロールには、印刷を開始するボタン、ズーム イン用のボタン、1 ページまたは複数ページを表示するボタン、およびダイアログ ボックスを閉じるためのボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99af8-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="99af8-106">キーのプロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="99af8-106">Key properties and methods</span></span>

<span data-ttu-id="99af8-107">コントロールのキープロパティは <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>であり、プレビューするドキュメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="99af8-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="99af8-108">ドキュメントは <xref:System.Drawing.Printing.PrintDocument> オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="99af8-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="99af8-109">ダイアログボックスを表示するには、<xref:System.Windows.Forms.Form.ShowDialog%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="99af8-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="99af8-110">アンチエイリアシングを使用すると、テキストを滑らかに表示できますが、表示速度が低下することもあります。これを使用するには、<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="99af8-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="99af8-111">特定のプロパティは、<xref:System.Windows.Forms.PrintPreviewDialog> に含まれる <xref:System.Windows.Forms.PrintPreviewControl> を通じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="99af8-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="99af8-112">(フォームにこの <xref:System.Windows.Forms.PrintPreviewControl> を追加する必要はありません。フォームにダイアログを追加すると、<xref:System.Windows.Forms.PrintPreviewDialog> 内に自動的に含まれます)。<xref:System.Windows.Forms.PrintPreviewControl> で使用できるプロパティの例としては、コントロール上で水平方向および垂直方向に表示されるページ数を決定する <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> と <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="99af8-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="99af8-113"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> プロパティには、Visual Basic の `PrintPreviewDialog1.PrintPreviewControl.Columns`、ビジュアルC#内の `printPreviewDialog1.PrintPreviewControl.Columns`、またはビジュアルC++での `printPreviewDialog1->PrintPreviewControl->Columns` としてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99af8-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="99af8-114">Printプレビューダイアログのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="99af8-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="99af8-115">次の条件下では、<xref:System.Windows.Forms.PrintPreviewDialog> コントロールの初期化が非常に遅くなります。</span><span class="sxs-lookup"><span data-stu-id="99af8-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="99af8-116">ネットワークプリンターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="99af8-116">A network printer is used.</span></span>
- <span data-ttu-id="99af8-117">このプリンターのユーザー設定 (二重設定など) は変更されます。</span><span class="sxs-lookup"><span data-stu-id="99af8-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="99af8-118">.NET Framework 4.5.2 で実行されているアプリでは、構成ファイルの \<appSettings > セクションに次のキーを追加して、<xref:System.Windows.Forms.PrintPreviewDialog> コントロールの初期化のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="99af8-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="99af8-119">`EnablePrintPreviewOptimization` キーが他の値に設定されている場合、またはキーが存在しない場合、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="99af8-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="99af8-120">.NET Framework 4.6 以降のバージョンで実行されているアプリでは、アプリ構成ファイルの[\<ランタイム >](../../configure-apps/file-schema/runtime/index.md)セクションの[\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)要素に次のスイッチを追加できます。</span><span class="sxs-lookup"><span data-stu-id="99af8-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="99af8-121">スイッチが存在しない場合、または他の値に設定されている場合、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="99af8-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="99af8-122"><xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> イベントを使用してプリンターの設定を変更した場合、最適化構成スイッチが設定されていても、<xref:System.Windows.Forms.PrintPreviewDialog> コントロールのパフォーマンスは向上しません。</span><span class="sxs-lookup"><span data-stu-id="99af8-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="99af8-123">参照</span><span class="sxs-lookup"><span data-stu-id="99af8-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="99af8-124">PrintPreviewControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="99af8-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="99af8-125">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="99af8-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="99af8-126">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="99af8-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
