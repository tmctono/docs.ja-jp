---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614850"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="9f980-101">Windows Workflow Foundation (WF) ワークフロー デザイナーでのアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="9f980-101">Accessibility improvements in Windows Workflow Foundation (WF) workflow designer</span></span>

#### <a name="details"></a><span data-ttu-id="9f980-102">説明</span><span class="sxs-lookup"><span data-stu-id="9f980-102">Details</span></span>

<span data-ttu-id="9f980-103">Windows Workflow Foundation (WF) ワークフロー デザイナーは、アクセシビリティ テクノロジによって操作性が向上しています。</span><span class="sxs-lookup"><span data-stu-id="9f980-103">The Windows Workflow Foundation (WF) workflow designer is improving how it works with accessibility technologies.</span></span> <span data-ttu-id="9f980-104">次のような改善点があります。</span><span class="sxs-lookup"><span data-stu-id="9f980-104">These improvements include the following changes:</span></span>

- <span data-ttu-id="9f980-105">一部のコントロールで、タブ オーダーが左から右、上から下に変更されます:</span><span class="sxs-lookup"><span data-stu-id="9f980-105">The tab order is changed to left to right and top to bottom in some controls:</span></span>
- <span data-ttu-id="9f980-106"><xref:System.ServiceModel.Activities.InitializeCorrelation> アクティビティの関連付けデータを設定するための関連付けの初期化ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9f980-106">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity</span></span>
- <span data-ttu-id="9f980-107"><xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティのコンテンツ定義ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9f980-107">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities</span></span>
- <span data-ttu-id="9f980-108">キーボードで利用できる機能が増えます:</span><span class="sxs-lookup"><span data-stu-id="9f980-108">More functions are available via the keyboard:</span></span>
- <span data-ttu-id="9f980-109">アクティビティのプロパティを編集する際、プロパティ グループに初めてフォーカスを設定したときに、プロパティ グループをキーボードで折りたたむことができます。</span><span class="sxs-lookup"><span data-stu-id="9f980-109">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>
- <span data-ttu-id="9f980-110">警告アイコンにキーボードでアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9f980-110">Warning icons are now accessible by keyboard.</span></span>
- <span data-ttu-id="9f980-111">[プロパティ] ウィンドウの [その他のプロパティ] ボタンに、キーボードでアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9f980-111">The More Properties button in the Properties window is now accessible by keyboard.</span></span>
- <span data-ttu-id="9f980-112">キーボードを使って、ワークフロー デザイナーの [引数] および [変数] ウィンドウのヘッダー項目にアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9f980-112">Keyboard users now can access the header items in the Arguments and Variables panes of the Workflow Designer.</span></span>
- <span data-ttu-id="9f980-113">次のような場合に、フォーカスのある項目の可視性が向上しました:</span><span class="sxs-lookup"><span data-stu-id="9f980-113">Improved visibility of items with focus, such as when:</span></span>
- <span data-ttu-id="9f980-114">ワークフロー デザイナーおよびアクティビティ デザイナーで使われているデータ グリッドへの行の追加。</span><span class="sxs-lookup"><span data-stu-id="9f980-114">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>
- <span data-ttu-id="9f980-115"><xref:System.ServiceModel.Activities.ReceiveReply> および <xref:System.ServiceModel.Activities.SendReply> アクティビティ内のフィールド間の Tab 移動。</span><span class="sxs-lookup"><span data-stu-id="9f980-115">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>
- <span data-ttu-id="9f980-116">変数または引数の既定値の設定</span><span class="sxs-lookup"><span data-stu-id="9f980-116">Setting default values for variables or arguments</span></span>
- <span data-ttu-id="9f980-117">スクリーン リーダーが正しく認識できるようになりました:</span><span class="sxs-lookup"><span data-stu-id="9f980-117">Screen readers can now correctly recognize:</span></span>
- <span data-ttu-id="9f980-118">ワークフロー デザイナーで設定されたブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="9f980-118">Breakpoints set in the workflow designer.</span></span>
- <span data-ttu-id="9f980-119"><xref:System.Activities.Statements.FlowSwitch%601>、<xref:System.Activities.Statements.FlowDecision>、<xref:System.ServiceModel.Activities.CorrelationScope> アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="9f980-119">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
- <span data-ttu-id="9f980-120"><xref:System.ServiceModel.Activities.Receive> アクティビティの内容。</span><span class="sxs-lookup"><span data-stu-id="9f980-120">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>
- <span data-ttu-id="9f980-121"><xref:System.Activities.Statements.InvokeMethod> アクティビティのターゲットの種類。</span><span class="sxs-lookup"><span data-stu-id="9f980-121">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>
- <span data-ttu-id="9f980-122"><xref:System.Activities.Statements.TryCatch> アクティビティの [例外] コンボ ボックスと [Finally] セクション。</span><span class="sxs-lookup"><span data-stu-id="9f980-122">The Exception combobox and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>
- <span data-ttu-id="9f980-123">メッセージング アクティビティの [メッセージの種類] コンボ ボックス、[関連付け初期化子の追加] ウィンドウのスプリッター、[コンテンツ定義] ウィンドウで、および [CorrelatesOn の定義] ウィンドウ (<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply>)。</span><span class="sxs-lookup"><span data-stu-id="9f980-123">The Message Type combobox, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Defintion window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>
- <span data-ttu-id="9f980-124">ステート マシンの遷移と遷移先。</span><span class="sxs-lookup"><span data-stu-id="9f980-124">State machine transitions and transitions destinations.</span></span>
- <span data-ttu-id="9f980-125"><xref:System.Activities.Statements.FlowDecision> アクティビティの注釈とコネクタ。</span><span class="sxs-lookup"><span data-stu-id="9f980-125">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>
- <span data-ttu-id="9f980-126">アクティビティのコンテキスト (右クリック) メニュー。</span><span class="sxs-lookup"><span data-stu-id="9f980-126">The context (right-click) menus for activities.</span></span>
- <span data-ttu-id="9f980-127">プロパティ グリッドの、プロパティ値エディター、[検索のクリア] ボタン、[カテゴリ別] および [アルファベット順] の並べ替えボタン、[式エディター] ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="9f980-127">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>
- <span data-ttu-id="9f980-128">ワークフロー デザイナーのズーム パーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="9f980-128">The zoom percentage in the Workflow Designer.</span></span>
- <span data-ttu-id="9f980-129"><xref:System.Activities.Statements.Parallel> および <xref:System.Activities.Statements.Pick> アクティビティの区切り記号。</span><span class="sxs-lookup"><span data-stu-id="9f980-129">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>
- <span data-ttu-id="9f980-130"><xref:System.Activities.Statements.InvokeDelegate> アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="9f980-130">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>
- <span data-ttu-id="9f980-131">ディクショナリ アクティビティの [型の選択] ウィンドウ (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`、`Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>` など)。</span><span class="sxs-lookup"><span data-stu-id="9f980-131">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>`, etc.).</span></span>
- <span data-ttu-id="9f980-132">[.NET 型の参照と選択] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="9f980-132">The Browse and Select .NET Type window.</span></span>
- <span data-ttu-id="9f980-133">ワークフロー デザイナーでの階層リンク。</span><span class="sxs-lookup"><span data-stu-id="9f980-133">Breadcrumbs in the Workflow Designer.</span></span>
- <span data-ttu-id="9f980-134">ハイ コントラスト テーマを選ぶと、要素間のコントラスト比の向上や、フォーカス要素に使われる選択ボックスの認識性の向上など、ワークフロー デザイナーとそのコントロールの表示について多くの点が向上していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9f980-134">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9f980-135">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9f980-135">Suggestion</span></span>

<span data-ttu-id="9f980-136">ワークフロー デザイナーが再ホストされたアプリケーションでは、次のいずれかを行うことでこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9f980-136">If you have an application with a re-hosted workflow designer, your application can benefit from these changes by performing either of these actions:</span></span>

- <span data-ttu-id="9f980-137">.NET Framework 4.7.1 を対象にしてアプリケーションを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="9f980-137">Recompile your application to target the .NET Framework 4.7.1.</span></span> <span data-ttu-id="9f980-138">これらのアクセシビリティの変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="9f980-138">These accessibility changes are enabled by default.</span></span>
- <span data-ttu-id="9f980-139">アプリケーションの対象が .NET Framework 4.7 以前であっても、.NET Framework 4.7.1 上で実行している場合は、次の [AppContext スイッチ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を app.config ファイルの `<runtime>` セクションに追加して `false` に設定することにより、従来のアクセシビリティ動作を無効にできます (次の例をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="9f980-139">If your application targets the .NET Framework 4.7 or earlier but is running on the .NET Framework 4.7.1, you can opt out of these legacy accessibility behaviors by adding the following [AppContext switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and set it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="9f980-140">.NET Framework 4.7.1 以降を対象とするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで以前のアクセシビリティ機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9f980-140">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="9f980-141">名前</span><span class="sxs-lookup"><span data-stu-id="9f980-141">Name</span></span>    | <span data-ttu-id="9f980-142">値</span><span class="sxs-lookup"><span data-stu-id="9f980-142">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9f980-143">スコープ</span><span class="sxs-lookup"><span data-stu-id="9f980-143">Scope</span></span>   | <span data-ttu-id="9f980-144">マイナー</span><span class="sxs-lookup"><span data-stu-id="9f980-144">Minor</span></span>       |
| <span data-ttu-id="9f980-145">バージョン</span><span class="sxs-lookup"><span data-stu-id="9f980-145">Version</span></span> | <span data-ttu-id="9f980-146">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9f980-146">4.7.1</span></span>       |
| <span data-ttu-id="9f980-147">種類</span><span class="sxs-lookup"><span data-stu-id="9f980-147">Type</span></span>    | <span data-ttu-id="9f980-148">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="9f980-148">Retargeting</span></span> |
