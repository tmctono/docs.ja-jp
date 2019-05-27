---
title: PrintPreviewDialog コントロールの概要 (Windows フォーム)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce6bf9cb9872183e60e6ccdf7eaf79b6630db51
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053694"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="dabc8-102">PrintPreviewDialog コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="dabc8-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="dabc8-103">Windows フォーム<xref:System.Windows.Forms.PrintPreviewDialog>コントロールは、構成済みのダイアログ ボックスを表示するために使用する方法、 [PrintDocument](printdocument-component-windows-forms.md)印刷されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabc8-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="dabc8-104">ダイアログ ボックスを構成する代わりに単純なソリューションとして、Windows ベースのアプリケーションの中で使用します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="dabc8-105">このコントロールには、印刷を開始するボタン、ズーム イン用のボタン、1 ページまたは複数ページを表示するボタン、およびダイアログ ボックスを閉じるためのボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dabc8-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="dabc8-106">キー プロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="dabc8-106">Key properties and methods</span></span>

<span data-ttu-id="dabc8-107">コントロールのキー プロパティは、<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>をプレビューするドキュメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="dabc8-108">ドキュメントがある必要があります、<xref:System.Drawing.Printing.PrintDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dabc8-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="dabc8-109">ダイアログ ボックスを表示するために呼び出す必要があるその<xref:System.Windows.Forms.Form.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="dabc8-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="dabc8-110">アンチエイリアシングが滑らかにテキストを行うことができますが、低速です。 表示することもできますが、これを使用する設定、<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="dabc8-111">特定のプロパティは、<xref:System.Windows.Forms.PrintPreviewControl>を<xref:System.Windows.Forms.PrintPreviewDialog>が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dabc8-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="dabc8-112">(これを追加する必要はありません<xref:System.Windows.Forms.PrintPreviewControl>フォームに自動的に格納されて、<xref:System.Windows.Forms.PrintPreviewDialog>ダイアログ ボックスをフォームに追加するとします)。利用できるプロパティの例については、<xref:System.Windows.Forms.PrintPreviewControl>は、<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>と<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>プロパティで、コントロールの水平および垂直を表示するページの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="dabc8-113">アクセスできる、<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>プロパティとして`PrintPreviewDialog1.PrintPreviewControl.Columns`Visual basic で`printPreviewDialog1.PrintPreviewControl.Columns`ビジュアルC#、または`printPreviewDialog1->PrintPreviewControl->Columns`ビジュアルでC++します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="dabc8-114">PrintPreviewDialog パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="dabc8-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="dabc8-115">次の条件下で、<xref:System.Windows.Forms.PrintPreviewDialog>コントロールは非常に遅くなりますを初期化します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="dabc8-116">ネットワーク プリンターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dabc8-116">A network printer is used.</span></span>
- <span data-ttu-id="dabc8-117">双方向の設定など、プリンターのユーザー設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="dabc8-118">アプリの .NET Framework 4.5.2 で実行されている場合に、次のキーを追加することができます、 \<appSettings > セクションのパフォーマンスを向上させるために、構成ファイルの<xref:System.Windows.Forms.PrintPreviewDialog>の初期化を制御します。</span><span class="sxs-lookup"><span data-stu-id="dabc8-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="dabc8-119">場合、`EnablePrintPreviewOptimization`キーが、他の値に設定されているか、キーが存在しない場合、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="dabc8-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="dabc8-120">アプリの .NET Framework 4.6 以降のバージョンで実行されている場合は、次のスイッチを追加することができます、 [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)内の要素、 [\<ランタイム >](../../configure-apps/file-schema/runtime/index.md)アプリ構成ファイルのセクション:</span><span class="sxs-lookup"><span data-stu-id="dabc8-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="dabc8-121">スイッチが存在しない場合、またはその他の値に設定されている場合は、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="dabc8-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="dabc8-122">使用する場合、<xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>のパフォーマンスのプリンターの設定を変更するイベント、<xref:System.Windows.Forms.PrintPreviewDialog>最適化の構成スイッチが設定されている場合でも、コントロールは改善されません。</span><span class="sxs-lookup"><span data-stu-id="dabc8-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="dabc8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dabc8-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="dabc8-124">PrintPreviewControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="dabc8-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="dabc8-125">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="dabc8-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="dabc8-126">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dabc8-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
