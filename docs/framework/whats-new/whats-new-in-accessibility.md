---
title: .NET Framework のアクセシビリティの新機能
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: 4dbc2024aa2e956b23030ae6eab987e65e006d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398677"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="da0a9-102">.NET Framework のアクセシビリティの新機能</span><span class="sxs-lookup"><span data-stu-id="da0a9-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="da0a9-103">.NET Framework では、ユーザーのためにアプリケーションのアクセシビリティ向上を目指しています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="da0a9-104">ユーザー補助機能により、支援機能の利用者にとってアプリケーションがさらに使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="da0a9-105">.NET Framework 4.7.1 以降、.NET Framework にはさまざまなアクセシビリティ機能改善が含まれるようになりました。それを利用することで開発者はアクセシビリティを備えたアプリケーションを開発できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-105">Starting with .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="da0a9-106">アクセシビリティのスイッチ</span><span class="sxs-lookup"><span data-stu-id="da0a9-106">Accessibility switches</span></span>

<span data-ttu-id="da0a9-107">アプリのターゲットが .NET Framework 4.7 である場合、またはそれより前のバージョンがターゲットであっても実行環境が .NET Framework 4.7.1 以降である場合は、ユーザー補助機能を使用するようにアプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-107">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="da0a9-108">また、アプリのターゲットが 4.7.1 .NET Framework 以降である場合は、従来の機能を使用するように (そして、ユーザー補助機能を利用しないように) アプリを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="da0a9-109">ユーザー補助機能が含まれる .NET Framework の各バージョンには、バージョン固有のアクセシビリティ スイッチがあります。これを、アプリケーションの構成ファイルの [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) セクションの [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="da0a9-110">サポートされているスイッチは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da0a9-110">The following are the supported switches:</span></span>

|<span data-ttu-id="da0a9-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="da0a9-111">Version</span></span>|<span data-ttu-id="da0a9-112">Switch</span><span class="sxs-lookup"><span data-stu-id="da0a9-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="da0a9-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="da0a9-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="da0a9-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="da0a9-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="da0a9-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="da0a9-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="da0a9-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="da0a9-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="da0a9-117">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="da0a9-117">.NET Framework 4.8</span></span>|<span data-ttu-id="da0a9-118">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="da0a9-118">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="da0a9-119">アクセシビリティ拡張機能の利用</span><span class="sxs-lookup"><span data-stu-id="da0a9-119">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="da0a9-120">.NET Framework 4.7.1 以降をターゲット対象とするアプリケーションでは、この新しいユーザー補助機能が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-120">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="da0a9-121">また、それより前のバージョンの .NET Framework がターゲットであっても、実行環境が .NET Framework 4.7.1 以降であるアプリケーションの場合は、アプリケーションの構成ファイルの [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) セクションの [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 要素にスイッチを追加し、値を `false` に設定することで、古いアクセシビリティ動作を利用しないことを (そして、それにより向上したアクセシビリティ機能改善を利用することを) 選択できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-121">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="da0a9-122">.NET Framework 4.7.1 で導入されたアクセシビリティの機能強化を有効にする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-122">The following shows how to opt in to accessibility enhancements introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="da0a9-123">新しいバージョンの .NET Framework のユーザー補助機能を選択する場合は、古いバージョンの .NET Framework の機能も明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-123">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="da0a9-124">.NET Framework 4.7.1 と 4.7.2 両方のアクセシビリティ機能改善を利用するようにアプリを構成するには、次の [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-124">Configuring your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="da0a9-125">.NET Framework 4.7.1、4.7.2、4.8 のアクセシビリティ機能改善を利用するようにアプリを構成するには、次の [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-125">Configuring your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, and 4.8 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="da0a9-126">従来の動作に戻す</span><span class="sxs-lookup"><span data-stu-id="da0a9-126">Restoring legacy behavior</span></span>

<span data-ttu-id="da0a9-127">アプリケーションがバージョン 4.7.1 以降の .NET Framework をターゲットにしている場合、アプリケーションの構成ファイルの [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) セクションの [`<runtime>`](../configure-apps/file-schema/runtime/index.md) 要素にスイッチを追加し、値を `true` に設定することで、アクセシビリティ機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-127">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="da0a9-128">たとえば、次の構成は、.NET Framework 4.7.2 で導入されたユーザー補助機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="da0a9-128">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="da0a9-129">.NET Framework 4.8 のアクセシビリティの新機能</span><span class="sxs-lookup"><span data-stu-id="da0a9-129">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="da0a9-130">.NET Framework 4.8 には、次の領域の新しいユーザー補助機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-130">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="da0a9-131">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="da0a9-131">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="da0a9-132">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-132">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="da0a9-133">Windows Workflow Foundation (WF) ワークフロー デザイナー</span><span class="sxs-lookup"><span data-stu-id="da0a9-133">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a><span data-ttu-id="da0a9-134">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="da0a9-134">Windows Forms</span></span>

<span data-ttu-id="da0a9-135">.NET Framework 4.8 では、多くの一般的に使用されているコントロールに対する LiveRegion と通知イベントのサポートが Windows フォームで追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-135">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="da0a9-136">ユーザーがキーボードを使用してコントロールに移動するときのツールヒントのサポートも追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-136">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="da0a9-137">**Label と StatusStrip の UIA LiveRegion サポート**</span><span class="sxs-lookup"><span data-stu-id="da0a9-137">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="da0a9-138">アプリケーション開発者は UIA LiveRegion を使用することで、ユーザーが作業しているところからは離れた場所にあるコントロールのテキスト変更をスクリーン リーダーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-138">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="da0a9-139">これは、たとえば接続状態を示す <xref:System.Windows.Forms.StatusStrip> コントロールなどで便利です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-139">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="da0a9-140">接続が切断されて状態が変わった場合に、開発者はスクリーン リーダーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-140">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="da0a9-141">.NET Framework 4.8 以降、Windows フォームでは <xref:System.Windows.Forms.Label> と <xref:System.Windows.Forms.StatusStrip> 両方のコントロールに対して UIA LiveRegion が実装されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-141">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="da0a9-142">たとえば、次のコードでは LiveRegion が <xref:System.Windows.Forms.Label>という名前の `label1` コントロールで使用されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-142">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="da0a9-143">ユーザーがアプリケーションの操作中であるかどうかに関わらず、ナレーターにより "Ready" と読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-143">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="da0a9-144"><xref:System.Windows.Forms.UserControl> を LiveRegion として実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-144">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

<span data-ttu-id="da0a9-145">**UIA 通知イベント**</span><span class="sxs-lookup"><span data-stu-id="da0a9-145">**UIA notification events**</span></span>

<span data-ttu-id="da0a9-146">Windows 10 Fall Creators Update で導入された UIA 通知イベントをアプリで使用すると、UIA イベントを発生させ、対応するコントロールを UI に準備することなく、イベント用に指定したテキストに基づいてナレーターに単純に読み上げさせることができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-146">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="da0a9-147">一部のシナリオでは、これはアプリのアクセシビリティを飛躍的に向上させる最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-147">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="da0a9-148">長時間かかる可能性のあるいくつかのプロセスの進行状況を通知するのにも便利です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-148">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="da0a9-149">UIA 通知イベントの詳細については、[デスクトップ アプリで新しい UI 通知イベントを使用する方法](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0a9-149">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need).</span></span>

<span data-ttu-id="da0a9-150">次の例では、[通知イベント](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A)を発生させています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-150">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="da0a9-151">**キーボード アクセスのツールヒント**</span><span class="sxs-lookup"><span data-stu-id="da0a9-151">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="da0a9-152">.NET Framework 4.7.2 以前のバージョンをターゲットとしたアプリケーションでは、[tooltip](xref:System.Windows.Forms.ToolTip) コントロールがポップ アップするようトリガーする唯一の方法は、マウス ポインターをそのコントロールに移動することでした。</span><span class="sxs-lookup"><span data-stu-id="da0a9-152">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="da0a9-153">.NET Framework 4.8 以降、キーボードを使用するユーザーは、Tab キーまたは方向キーを修飾キーと共に、または修飾キーなしで使用してコントロールにフォーカスすることで、コントロールのツールヒントをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-153">Starting with .NET Framework 4.8, a keyboard user can trigger a control’s tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="da0a9-154">この特別なアクセシビリティの機能強化には、追加の [AppContext スイッチ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)が必要となります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-154">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="da0a9-155">次の図は、ユーザーがキーボードを使用してボタンを選択したときのツールヒントを示しています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-155">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![ユーザーがキーボードを使用してボタンに移動したときのツールヒントのスクリーンショット。](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="da0a9-157">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-157">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="da0a9-158">.NET Framework 4.8 以降、WPF に数多くのアクセシビリティ機能改善が導入されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-158">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="da0a9-159">**可視性が Collapsed または Hidden の要素はスクリーン ナレーターで読み上げられない**</span><span class="sxs-lookup"><span data-stu-id="da0a9-159">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="da0a9-160">可視性が Collapsed または Hidden の要素は、スクリーン リーダーによって読み上げられなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-160">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="da0a9-161">可視性が <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> または <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> の要素を含むユーザー インターフェイスは、スクリーン リーダーによってユーザーに読み上げるときに誤って伝わる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-161">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="da0a9-162">.NET Framework 4.8 以降、WPF では UIAutomation ツリーのコントロール ビューに Collapsed または Hidden の要素は含まれないため、スクリーン リーダーによってこれらの要素が読み上げられることは今後ありません。</span><span class="sxs-lookup"><span data-stu-id="da0a9-162">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="da0a9-163">**非装飾ベースのテキスト選択での SelectionTextBrush プロパティの使用**</span><span class="sxs-lookup"><span data-stu-id="da0a9-163">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="da0a9-164">.NET Framework 4.7.2 では、装飾層を使用せずに <xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.PasswordBox> テキスト選択を描画する機能が WPF に追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-164">In the .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="da0a9-165">このシナリオでは、選択したテキストの前景色は <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType> により指定されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-165">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="da0a9-166">.NET Framework 4.8 で追加された新しいプロパティ `SelectionTextBrush` を使用すると、開発者は非装飾ベースのテキスト選択を使用する場合に、選択したテキストに対して特定のブラシを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-166">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="da0a9-167">このプロパティは、非装飾ベースのテキスト選択が有効な WPF アプリケーション内の <xref:System.Windows.Controls.Primitives.TextBoxBase> から派生したコントロールと <xref:System.Windows.Controls.PasswordBox> コントロールでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-167">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="da0a9-168"><xref:System.Windows.Controls.RichTextBox> コントロールでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="da0a9-168">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="da0a9-169">非装飾ベースのテキスト選択が有効ではない場合、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-169">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="da0a9-170">このプロパティを使用するには、単に XAML コードに追加して、適切なブラシまたはバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-170">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="da0a9-171">結果のテキスト選択は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-171">The resulting text selection looks like this:</span></span>

![実行中のアプリのスクリーンショット。Hello World という言葉が選択されています。](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

<span data-ttu-id="da0a9-173">`SelectionBrush` と `SelectionTextBrush` プロパティを組み合わせて使用することで、背景色と前景色の適切な組み合わせを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-173">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="da0a9-174">**UIAutomation ControllerFor プロパティのサポート**</span><span class="sxs-lookup"><span data-stu-id="da0a9-174">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="da0a9-175">UIAutomation の `ControllerFor` プロパティは、このプロパティをサポートするオートメーション要素によって操作されるオートメーション要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-175">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="da0a9-176">このプロパティは通常、自動提案アクセシビリティで使用されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-176">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="da0a9-177">`ControllerFor`は、オートメーション要素がアプリケーション UI またはデスクトップの 1 つ以上のセグメントに影響する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-177">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="da0a9-178">それ以外の場合、コントロール操作の影響を UI 要素と関連付けることは困難です。</span><span class="sxs-lookup"><span data-stu-id="da0a9-178">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="da0a9-179">この機能により、コントロールで `ControllerFor`プロパティの値を指定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-179">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="da0a9-180">.NET Framework 4.8 では、新しい仮想メソッド <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType> が追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-180">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-181">`ControllerFor` プロパティの値を指定するには、単にこのメソッドをオーバーライドして、この `List<AutomationPeer>` で操作されているコントロールの <xref:System.Windows.Automation.Peers.AutomationPeer> を返します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-181">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

<span data-ttu-id="da0a9-182">**キーボード アクセスのツールヒント**</span><span class="sxs-lookup"><span data-stu-id="da0a9-182">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="da0a9-183">.NET Framework 4.7.2 以前のバージョンでは、ツールヒントはユーザーがマウス カーソルをコントロールの上に置いたときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-183">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="da0a9-184">.NET Framework 4.8 では、ツールヒントはキーボード フォーカス上に、そしてキーボード ショートカットによっても表示されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-184">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="da0a9-185">この機能を使用するには、アプリケーションで .NET Framework 4.8 をターゲットとするか、または `Switch.UseLegacyAccessibilityFeatures.3` と `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを使用してオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-185">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="da0a9-186">サンプルのアプリケーション構成ファイルを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-186">The following is a sample application configuration file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

<span data-ttu-id="da0a9-187">一度有効にすると、ツールヒントを含むすべてのコントロールで、キーボード フォーカスをコントロールが受けるとツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-187">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="da0a9-188">ツールヒントは時間が経過したとき、またはキーボード フォーカスが変わったときに、消すことができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-188">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="da0a9-189">ユーザーは新しいキーボード ショートカット Ctrl + Shift + F10 を使用してツールヒントを手動で消すこともできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-189">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="da0a9-190">ツールヒントが消えたら、同じキーボード ショートカットを使用して再度表示することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-190">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="da0a9-191">[ コントロール上の ](xref:System.Windows.Controls.Ribbon.RibbonToolTip)リボンのツールヒント<xref:System.Windows.Controls.Ribbon.Ribbon>は、キーボード フォーカスに表示されません。キーボード ショートカットでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-191">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="da0a9-192">**UIAutomation プロパティの SizeOfSet および PositionInSet のサポートを追加**</span><span class="sxs-lookup"><span data-stu-id="da0a9-192">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="da0a9-193">Windows 10 では 2 つの新しい UIAutomation プロパティである `SizeOfSet` と `PositionInSet` が導入されました。アプリケーションで使用してセット内の項目数を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-193">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="da0a9-194">スクリーン リーダーなどの UIAutomation クライアント アプリケーションは、これらのプロパティに関してアプリケーションに照会して、アプリケーションの UI の正確な表記を読み上げることができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-194">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="da0a9-195">.NET Framework 4.8 以降、WPF ではこれら 2 つのプロパティが WPF アプリケーションの UIAutomation に公開されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-195">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="da0a9-196">その方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-196">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="da0a9-197">依存関係プロパティを使用。</span><span class="sxs-lookup"><span data-stu-id="da0a9-197">By using dependency properties.</span></span>

  <span data-ttu-id="da0a9-198">WPF では 2 つの新しい依存関係プロパティである <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> と <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType> が追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-198">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-199">開発者は XAML を使用してその値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-199">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="da0a9-200">AutomationPeer 仮想メソッドをオーバーライド。</span><span class="sxs-lookup"><span data-stu-id="da0a9-200">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="da0a9-201"><xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> と <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> 仮想メソッドが、AutomationPeer クラスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-201">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="da0a9-202">次の例に示すように、開発者はこれらのメソッドをオーバーライドすることで、`SizeOfSet` と `PositionInSet` の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-202">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

<span data-ttu-id="da0a9-203">さらに、<xref:System.Windows.Controls.ItemsControl> インスタンス内の項目により、これらのプロパティの値を自動的に、開発者による追加のアクションなしで指定することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-203">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="da0a9-204"><xref:System.Windows.Controls.ItemsControl> がグループ化されている場合、グループのコレクションはセットとして表されます。各グループは別々のセットとしてカウントされ、グループ内の各項目ではグループ内の自身の位置とグループのサイズが示されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-204">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="da0a9-205">自動値は仮想化によって影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="da0a9-205">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="da0a9-206">項目は実現されていない場合でも、セットの合計サイズに含まれ、その兄弟項目のセット内の位置に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-206">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="da0a9-207">自動値は、アプリケーションが .NET Framework 4.8 をターゲットとしている場合のみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-207">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="da0a9-208">以前のバージョンの .NET Framework をターゲットとするアプリケーションの場合は、次の App.config ファイルに示すように、`Switch.UseLegacyAccessibilityFeatures.3` [AppContext スイッチ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-208">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48" />

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="da0a9-209">Windows Workflow Foundation (WF) ワークフロー デザイナー</span><span class="sxs-lookup"><span data-stu-id="da0a9-209">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="da0a9-210">.NET Framework 4.8 ではワークフロー デザイナーに次の変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-210">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="da0a9-211">ナレーターを使用するユーザー向けの、FlowSwitch case ラベルの改善。</span><span class="sxs-lookup"><span data-stu-id="da0a9-211">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="da0a9-212">ナレーターを使用するユーザー向けの、ボタン説明の改善。</span><span class="sxs-lookup"><span data-stu-id="da0a9-212">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="da0a9-213">ハイ コントラスト テーマを選ぶユーザー向けの、要素間のコントラスト比の向上や、フォーカス要素に使われる選択ボックスの認識性の向上など、ワークフロー デザイナーとそのコントロールの表示に関する改善。</span><span class="sxs-lookup"><span data-stu-id="da0a9-213">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="da0a9-214">アプリケーションが .NET Framework 4.7.2 以前のバージョンをターゲットとしている場合、アプリケーション構成ファイルで `Switch.UseLegacyAccessibilityFeatures.3` [AppContext スイッチ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を `false` に設定することで、これらの変更にオプトインすることができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-214">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="da0a9-215">詳細については、この記事の「[アクセシビリティ拡張機能の利用](#taking-advantage-of-accessibility-enhancements)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0a9-215">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="da0a9-216">.NET Framework 4.7.2 のアクセシビリティの新機能</span><span class="sxs-lookup"><span data-stu-id="da0a9-216">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="da0a9-217">.NET Framework 4.7.2 には、次の領域の新しいユーザー補助機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-217">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="da0a9-218">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="da0a9-218">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="da0a9-219">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-219">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="da0a9-220">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="da0a9-220">Windows Forms</span></span>

<span data-ttu-id="da0a9-221">**ハイ コントラスト テーマでの OS で定義された色**</span><span class="sxs-lookup"><span data-stu-id="da0a9-221">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="da0a9-222">.NET Framework 4.7.2 以降、Windows フォームは、オペレーティング システムで定義されている色をハイ コントラスト テーマで使用します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-222">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="da0a9-223">これは、次のコントロールに影響します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-223">This affects the following controls:</span></span>

- <span data-ttu-id="da0a9-224"><xref:System.Windows.Forms.ToolStripDropDownButton> コントロールのドロップダウン矢印。</span><span class="sxs-lookup"><span data-stu-id="da0a9-224">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="da0a9-225"><xref:System.Windows.Forms.Button> が <xref:System.Windows.Forms.RadioButton> または <xref:System.Windows.Forms.CheckBox> に設定された、<xref:System.Windows.Forms.ButtonBase.FlatStyle>、<xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType>、および <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> コントロール。</span><span class="sxs-lookup"><span data-stu-id="da0a9-225">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-226">以前は、選択されたテキストと背景の色のコントラストが同じで、見分けるのが困難でした。</span><span class="sxs-lookup"><span data-stu-id="da0a9-226">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="da0a9-227"><xref:System.Windows.Forms.GroupBox> プロパティが <xref:System.Windows.Forms.Control.Enabled> に設定されている `false` に含まれるコントロール。</span><span class="sxs-lookup"><span data-stu-id="da0a9-227">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="da0a9-228"><xref:System.Windows.Forms.ToolStripButton>、<xref:System.Windows.Forms.ToolStripComboBox>、<xref:System.Windows.Forms.ToolStripDropDownButton> コントロール。これらは、ハイ コントラスト モードでの明度コントラストの比率が高くなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-228">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="da0a9-229"><xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> の <xref:System.Windows.Forms.DataGridViewLinkCell> プロパティ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-229">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="da0a9-230">**ナレーターの機能強化**</span><span class="sxs-lookup"><span data-stu-id="da0a9-230">**Narrator improvements**</span></span>

<span data-ttu-id="da0a9-231">.NET Framework 4.7.2 以降では、ナレーターのサポートが次のように強化されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-231">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="da0a9-232"><xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> のテキストを読み上げるときに、<xref:System.Windows.Forms.ToolStripMenuItem> プロパティの値を読み上げます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-232">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="da0a9-233"><xref:System.Windows.Forms.ToolStripMenuItem> の <xref:System.Windows.Forms.Control.Enabled> プロパティが `false` に設定されている場合、それを示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-233">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="da0a9-234"><xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> プロパティが `true` に設定されているとき、チェック ボックスの状態に関するフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-234">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="da0a9-235">ナレーター スキャン モードのフォーカス順序が、ClickOnce ダウンロード ダイアログ ウィンドウでのコントロールの視覚的な順序と一致します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-235">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="da0a9-236">**DataGridView の機能強化**</span><span class="sxs-lookup"><span data-stu-id="da0a9-236">**DataGridView improvements**</span></span>

<span data-ttu-id="da0a9-237">.NET Framework 4.7.2 以降、<xref:System.Windows.Forms.DataGridView> コントロールには次のアクセシビリティ機能改善が導入されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-237">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="da0a9-238">キーボードを使って行を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-238">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="da0a9-239">ユーザーは、F3 キーを使って現在の列で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-239">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="da0a9-240"><xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> が <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> に設定されていると、ユーザーが現在の行のセルを Tab で移動するとき、列ヘッダーの色が変わって現在の列を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-240">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="da0a9-241"><xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> の <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> プロパティは、正しい親コントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-241">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="da0a9-242">**視覚的な手掛かりの向上**</span><span class="sxs-lookup"><span data-stu-id="da0a9-242">**Improved visual cues**</span></span>

- <span data-ttu-id="da0a9-243"><xref:System.Windows.Forms.RadioButton> プロパティが空の <xref:System.Windows.Forms.CheckBox> および <xref:System.Windows.Forms.ButtonBase.Text> コントロールは、フォーカスを受け取るとフォーカス インジケーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-243">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="da0a9-244">**強化されたプロパティ グリッドのサポート**</span><span class="sxs-lookup"><span data-stu-id="da0a9-244">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="da0a9-245"><xref:System.Windows.Forms.PropertyGrid> コントロールの子要素は、PropertyGrid 要素が有効になっている場合にのみ、`true` プロパティに対して <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> を返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-245">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="da0a9-246"><xref:System.Windows.Forms.PropertyGrid> コントロールの子要素は、PropertyGrid 要素をユーザーが変更できる場合にのみ、`false` プロパティに対して <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> を返します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-246">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="da0a9-247">**キーボード ナビゲーションの向上**</span><span class="sxs-lookup"><span data-stu-id="da0a9-247">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="da0a9-248"><xref:System.Windows.Forms.ToolStripButton> コントロールは、<xref:System.Windows.Forms.ToolStripPanel> プロパティが <xref:System.Windows.Forms.ToolStripPanel.TabStop> に設定された `true` 内に含まれているときにフォーカスできます</span><span class="sxs-lookup"><span data-stu-id="da0a9-248">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="da0a9-249">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-249">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="da0a9-250">**CheckBox および RadioButton コントロールに対する変更**</span><span class="sxs-lookup"><span data-stu-id="da0a9-250">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="da0a9-251">.NET Framework 4.7.1 以前のバージョンでは、WPF の <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> および <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> コントロールのフォーカス ビジュアルに整合性がなく、クラシック テーマとハイ コントラスト テーマでは正しくありません。</span><span class="sxs-lookup"><span data-stu-id="da0a9-251">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="da0a9-252">これらの問題は、コントロールに内容が何も設定されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-252">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="da0a9-253">これにより、テーマ間の遷移が混乱し、フォーカス ビジュアルが見にくくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-253">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="da0a9-254">.NET Framework 4.7.2 では、これらのビジュアルのテーマ間の整合性が向上し、クラシック モードとハイ コントラスト テーマでの視認性がよくなっています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-254">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="da0a9-255">**WPF アプリケーションでホストされる WinForms コントロール**</span><span class="sxs-lookup"><span data-stu-id="da0a9-255">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="da0a9-256">.NET Framework 4.7.1 以前のバージョンの WPF アプリケーションでホストされている WinForms コントロールでは、そのレイヤーの最初または最後のコントロールが WPF <xref:System.Windows.Forms.Integration.ElementHost> コントロールの場合、ユーザーは Tab キーで WinForms レイヤーから外に移動できませんでした。</span><span class="sxs-lookup"><span data-stu-id="da0a9-256">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="da0a9-257">.NET Framework 4.7.2 では、ユーザーは Tab キーで WinForms レイヤーから外に移動できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-257">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="da0a9-258">ただし、WinForms レイヤーをエスケープしないフォーカスに依存する自動化アプリケーションは、意図したように機能しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-258">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="da0a9-259">.NET Framework 4.7.1 のアクセシビリティの新機能</span><span class="sxs-lookup"><span data-stu-id="da0a9-259">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="da0a9-260">.NET Framework 4.7.1 には、次の領域の新しいユーザー補助機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-260">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="da0a9-261">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-261">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="da0a9-262">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="da0a9-262">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="da0a9-263">ASP.NET Web コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-263">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="da0a9-264">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="da0a9-264">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="da0a9-265">Windows Workflow Foundation (WF) ワークフロー デザイナー</span><span class="sxs-lookup"><span data-stu-id="da0a9-265">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="da0a9-266">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="da0a9-266">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="da0a9-267">**スクリーン リーダーの機能強化**</span><span class="sxs-lookup"><span data-stu-id="da0a9-267">**Screen reader improvements**</span></span>

<span data-ttu-id="da0a9-268">アクセシビリティ機能改善を有効にすると、.NET Framework 4.7.1 は次の面でスクリーン リーダーの機能を強化します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-268">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="da0a9-269">.NET Framework 4.7 以前のバージョンでは、<xref:System.Windows.Controls.Expander> コントロールはスクリーン リーダーによってボタンとして読み上げられました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-269">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="da0a9-270">.NET Framework 4.7.1 以降では、展開と折りたたみが可能なグループとして正しく読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-270">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="da0a9-271">.NET Framework 4.7 以前のバージョンでは、<xref:System.Windows.Controls.DataGridCell> コントロールはスクリーン リーダーによって "カスタム" として読み上げられました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-271">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="da0a9-272">.NET Framework 4.7.1 以降では、データ グリッド セル (ローカライズされます) として正しく読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-272">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="da0a9-273">.NET Framework 4.7.1 以降、スクリーン リーダーによって編集可能な <xref:System.Windows.Controls.ComboBox> の名前が読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-273">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="da0a9-274">.NET Framework 4.7 以前のバージョンの場合、<xref:System.Windows.Controls.PasswordBox> コントロールが "ビューに項目がありません" として読み上げられたか、他の誤動作が発生しました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-274">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="da0a9-275">この問題は .NET Framework 4.7.1 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-275">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="da0a9-276">**UIAutomation LiveRegion サポート**</span><span class="sxs-lookup"><span data-stu-id="da0a9-276">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="da0a9-277">ナレーターなどのスクリーン リーダーはアプリケーションの UI コンテンツをユーザーのために読み上げます。通常、フォーカスを合わせた UI コンテンツのテキストが読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-277">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="da0a9-278">ただし、UI 要素が変わり、フォーカスがなくなったとき、ユーザーに通知されず、重要な情報を逃すことがあります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-278">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="da0a9-279">ライブ領域は、この問題の解決を目指しています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-279">Live regions aim at solving this problem.</span></span> <span data-ttu-id="da0a9-280">開発者はこれを利用し、UI 要素が大幅に変更されたことをスクリーン リーダーやその他の UIAutomation クライアントに指示できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-280">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="da0a9-281">指示後、スクリーン リーダーでは、その変更をユーザーに通知する方法とタイミングが決定されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-281">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="da0a9-282">ライブ領域をサポートするために、次の API が WPF に追加されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-282">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="da0a9-283"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> フィールドと <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> フィールド。**LiveSetting** プロパティと **LiveRegionChanged** イベントを識別します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-283">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="da0a9-284">XAML を利用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-284">They can be set by using XAML.</span></span>

- <span data-ttu-id="da0a9-285">**AutomationProperties.LiveSetting** 添付プロパティ。UI の変化がユーザーにとって重要であることをスクリーン リーダーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-285">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="da0a9-286"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> プロパティ。**AutomationProperties.LiveSetting** 添付プロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-286">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="da0a9-287"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> メソッド。**LiveSetting** 値を提供するようにオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-287">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="da0a9-288"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> メソッドと <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> メソッド。**LiveSetting** 値を取得し、設定します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-288">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="da0a9-289"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 列挙。次の指定可能 **LiveSetting** 値を定義します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-289">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="da0a9-290">[https://login.microsoftonline.com/consumers/](<xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="da0a9-290"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-291">ライブ領域の内容が変更された場合でも、要素が通知を送信することはありません。</span><span class="sxs-lookup"><span data-stu-id="da0a9-291">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="da0a9-292">[https://login.microsoftonline.com/consumers/](<xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="da0a9-292"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-293">ライブ領域の内容が変更された場合、要素は非割り込み型の通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-293">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="da0a9-294">[https://login.microsoftonline.com/consumers/](<xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="da0a9-294"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da0a9-295">ライブ領域の内容が変更された場合、要素により割り込み通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-295">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="da0a9-296">関心のある要素で **AutomationProperties.LiveSetting** プロパティを作成できます。次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da0a9-296">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="da0a9-297">ライブ領域のデータが変化し、スクリーン リーダーに通知する必要があれば、次のサンプルのように、明示的にイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-297">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="da0a9-298">**ハイ コントラスト**</span><span class="sxs-lookup"><span data-stu-id="da0a9-298">**High contrast**</span></span>

<span data-ttu-id="da0a9-299">.NET Framework 4.7.1 以降、さまざまな WPF コントロールでハイ コントラストが強化されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-299">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="da0a9-300"><xref:System.Windows.SystemParameters.HighContrast%2A> テーマが設定されているときにこれを確認できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-300">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="da0a9-301">チェックの内容は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="da0a9-301">These include:</span></span>

- <span data-ttu-id="da0a9-302"><xref:System.Windows.Controls.Expander> コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-302"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="da0a9-303">フォーカスを合わせたとき、<xref:System.Windows.Controls.Expander> コントロールが見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-303">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="da0a9-304"><xref:System.Windows.Controls.ComboBox>、<xref:System.Windows.Controls.ListBox>、<xref:System.Windows.Controls.RadioButton> コントロールのキーボードも見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-304">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="da0a9-305">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-305">For example:</span></span>

  <span data-ttu-id="da0a9-306">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-306">Before:</span></span>

  ![展開コントロールのスクリーンショット。フォーカスありとフォーカスなしのビジュアル。](./media/whats-new-in-accessibility/expander-control-before.png)

  <span data-ttu-id="da0a9-308">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-308">After:</span></span>

  ![展開コントロールのスクリーンショット。コントロールのテキストが点線で囲まれています。](./media/whats-new-in-accessibility/expander-control-after.png)

- <span data-ttu-id="da0a9-310"><xref:System.Windows.Controls.CheckBox> コントロールと <xref:System.Windows.Controls.RadioButton> コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-310"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="da0a9-311"><xref:System.Windows.Controls.CheckBox> コントロールと <xref:System.Windows.Controls.RadioButton> コントロールのテキストは、ハイ コントラスト テーマで選択されているとき、見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-311">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="da0a9-312">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-312">For example:</span></span>

  <span data-ttu-id="da0a9-313">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-313">Before:</span></span>

  ![ラジオ ボタンとチェック ボタンのスクリーンショット。ハイ コントラストのテーマでテキストが読みにくくなっています。](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  <span data-ttu-id="da0a9-315">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-315">After:</span></span>

  ![ラジオ ボタンとチェック ボタンのスクリーンショット。ハイ コントラストのテーマでテキストが読みやすくなっています。](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <span data-ttu-id="da0a9-317"><xref:System.Windows.Controls.ComboBox> コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-317"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="da0a9-318">.NET Framework 4.7.1 以降、無効にした <xref:System.Windows.Controls.ComboBox> コントロールの枠線が無効にしたテキストと同じ色になります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-318">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="da0a9-319">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-319">For example:</span></span>

  <span data-ttu-id="da0a9-320">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-320">Before:</span></span>

  ![無効になっている ComboBox のスクリーンショット。さまざまな色の罫線とコントロール テキスト。](./media/whats-new-in-accessibility/combo-disabled-before.png)

  <span data-ttu-id="da0a9-322">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-322">After:</span></span>

  ![無効になっている ComboBox のスクリーンショット。罫線とコントロール テキストが同じ色です。](./media/whats-new-in-accessibility/combo-disabled-after.png)

  <span data-ttu-id="da0a9-324">また、無効にしているボタンにフォーカスを合わせたとき、正しいテーマ色が使用されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-324">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="da0a9-325">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-325">Before:</span></span>

  ![黒色ボタンのスクリーンショット。"Focus Me" というテキストが灰色です。](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  <span data-ttu-id="da0a9-327">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-327">After:</span></span>

  ![青色ボタンのスクリーンショット。"Focus Me" というテキストが黒色です。](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  <span data-ttu-id="da0a9-329">最後になりますが、.NET Framework 4.7 以前のバージョンでは、<xref:System.Windows.Controls.ComboBox> コントロールのスタイルを `Toolbar.ComboBoxStyleKey` に設定すると、ドロップダウンの矢印が見えなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-329">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="da0a9-330">この問題は .NET Framework 4.7.1 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-330">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="da0a9-331">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-331">For example:</span></span>

  <span data-ttu-id="da0a9-332">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-332">Before:</span></span>

  ![ComboBox コントロールのスクリーンショット。ドロップダウンの矢印が見えません。](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  <span data-ttu-id="da0a9-334">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-334">After:</span></span>

  ![ComboBox コントロールのスクリーンショット。ドロップダウンの矢印が見えます。](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- <span data-ttu-id="da0a9-336"><xref:System.Windows.Controls.DataGrid> コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-336"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="da0a9-337">.NET Framework 4.7.1 以降、<xref:System.Windows.Controls.DataGrid> コントロールの並べ替えインジケーターで正しいテーマ色が使われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-337">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="da0a9-338">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-338">For example:</span></span>

  <span data-ttu-id="da0a9-339">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-339">Before:</span></span>

  ![並べ替えインジケーター矢印のスクリーンショット (機能改善前)](./media/whats-new-in-accessibility/sort-indicator-before.png)

  <span data-ttu-id="da0a9-341">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-341">After:</span></span>

  ![並べ替えインジケーター矢印のスクリーンショット (機能改善後)](./media/whats-new-in-accessibility/sort-indicator-after.png)

  <span data-ttu-id="da0a9-343">また、.NET Framework 4.7 以前のバージョンでは、ハイ コントラスト モードでカーソルを合わせたとき、既定のリンク スタイルが正しくない色に変化しました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-343">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="da0a9-344">これは .NET Framework 4.7.1 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-344">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="da0a9-345">同様に、.NET Framework 4.7.1 以降、<xref:System.Windows.Controls.DataGrid> チェックボックス列でキーボード フォーカス フィードバックに既定の色が使用されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-345">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="da0a9-346">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-346">Before:</span></span>

  ![リンクのスクリーンショット。"Click Me!" という文字を](./media/whats-new-in-accessibility/default-link-style-before.png)

  <span data-ttu-id="da0a9-349">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-349">After:</span></span>

  ![リンクのスクリーンショット。"Click Me!" という文字を](./media/whats-new-in-accessibility/default-link-style-after.png)

<span data-ttu-id="da0a9-352">.NET Framework 4.7.1 での WPF アクセシビリティ機能改善の詳細については、「[WPF でのアクセシビリティの向上](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0a9-352">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="da0a9-353">Windows フォームのアクセシビリティ機能改善</span><span class="sxs-lookup"><span data-stu-id="da0a9-353">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="da0a9-354">.NET Framework 4.7.1 では、Windows フォーム (WinForms) のアクセシビリティが次の領域で変更されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-354">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="da0a9-355">**ハイ コントラスト モードの表示が改善されました**</span><span class="sxs-lookup"><span data-stu-id="da0a9-355">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="da0a9-356">.NET Framework 4.7.1 以降では、オペレーティング システムで利用できるハイ コントラスト モードを選択したとき、さまざまな WinForms コントロールの表示が改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-356">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="da0a9-357">Windows 10 では、ハイ コントラストのシステム色の一部で値が変わりました。Windows フォームは Windows 10 Win32 フレームワークに基づきます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-357">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="da0a9-358">最も快適に利用するためには、最新版の Windows で実行し、テスト アプリケーションに app.manifest ファイルを追加して最新の OS 変更を選択し、次の画像のように Windows 10 対応 OS 行のコメントを解除します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-358">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

<span data-ttu-id="da0a9-359">ハイ コントラストの変更例:</span><span class="sxs-lookup"><span data-stu-id="da0a9-359">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="da0a9-360"><xref:System.Windows.Forms.MenuStrip> 項目のチェックマークが見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-360">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="da0a9-361">選択したとき、無効になっている <xref:System.Windows.Forms.MenuStrip> 項目が見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-361">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="da0a9-362">選択した <xref:System.Windows.Forms.Button> コントロールのテキストが背景色に対して際立ち、見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-362">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="da0a9-363">無効になっているテキストが読みやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-363">Disabled text is easier to read.</span></span> <span data-ttu-id="da0a9-364">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-364">For example:</span></span>

  <span data-ttu-id="da0a9-365">次の処理の前</span><span class="sxs-lookup"><span data-stu-id="da0a9-365">Before:</span></span>

  ![ハイ コントラスト モードでさまざまなコントロールを使用するアプリのスクリーンショット (アクセシビリティ前)。](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  <span data-ttu-id="da0a9-367">後:</span><span class="sxs-lookup"><span data-stu-id="da0a9-367">After:</span></span>

  ![ハイ コントラスト モードでさまざまなコントロールを使用するアプリのスクリーンショット (アクセシビリティ後)。](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

- <span data-ttu-id="da0a9-369">スレッド例外ダイアログのハイ コントラストが改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-369">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="da0a9-370">**ナレーター サポートが改善されました**</span><span class="sxs-lookup"><span data-stu-id="da0a9-370">**Improved Narrator support**</span></span>

<span data-ttu-id="da0a9-371">.NET Framework 4.7.1 の Windows フォームでは、ナレーターのアクセシビリティが次の面で改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-371">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="da0a9-372"><xref:System.Windows.Forms.MonthCalendar> コントロールに、他の UI 自動化ツールと同様に、ナレーターからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-372">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="da0a9-373"><xref:System.Windows.Forms.CheckedListBox> コントロールは、項目のチェック状態が変わったとき、ナレーターに通知します。その結果、リスト アイテムの値を変えたことがユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-373">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="da0a9-374"><xref:System.Windows.Forms.DataGridViewCell> コントロールは正しい読み取り専用状態をナレーターに報告します。</span><span class="sxs-lookup"><span data-stu-id="da0a9-374">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="da0a9-375">ナレーターが無効になっている <xref:System.Windows.Forms.ToolStripMenuItem> テキストを読み上げるようになりました。以前は、無効になっているメニュー項目はスキップされました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-375">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="da0a9-376">**UIAutomation アクセシビリティ パターンのサポートが強化されました**</span><span class="sxs-lookup"><span data-stu-id="da0a9-376">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="da0a9-377">.NET Framework 4.7.1 以降、アクセシビリティ技術ツールの開発者は、一部の WinForms コントロールについて、API アクセシビリティの共通のパターンとプロパティを活用できます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-377">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="da0a9-378">アクセシビリティ機能改善の例:</span><span class="sxs-lookup"><span data-stu-id="da0a9-378">These accessibility improvements include:</span></span>

- <span data-ttu-id="da0a9-379"><xref:System.Windows.Forms.ComboBox> と <xref:System.Windows.Forms.ToolStripSplitButton> が[展開/折りたたみパターン](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)対応になりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-379">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="da0a9-380"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> が[切り替えパターン](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)対応になりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-380">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="da0a9-381"><xref:System.Windows.Forms.ToolStripItem> コントロールが <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> プロパティと[展開/折りたたみパターン](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)対応になりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-381">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="da0a9-382"><xref:System.Windows.Forms.NumericUpDown> コントロールと <xref:System.Windows.Forms.DomainUpDown> コントロールが <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> プロパティ対応になりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-382">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="da0a9-383">**プロパティ ブラウザーが使いやすくなりました**</span><span class="sxs-lookup"><span data-stu-id="da0a9-383">**Improved property browser experience**</span></span>

<span data-ttu-id="da0a9-384">.NET Framework 4.7.1 以降、Windows フォームは次の点で改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-384">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="da0a9-385">さまざまなドロップダウン選択ウィンドウを利用することでキーボード操作が便利になりました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-385">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="da0a9-386">不要なタブ ストップが減りました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-386">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="da0a9-387">コントロールの種類の報告機能が改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-387">Better reporting of control types.</span></span>
- <span data-ttu-id="da0a9-388">ナレーターの動作が改善されました。</span><span class="sxs-lookup"><span data-stu-id="da0a9-388">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="da0a9-389">ASP.NET Web コントロール</span><span class="sxs-lookup"><span data-stu-id="da0a9-389">ASP.NET web controls</span></span>

<span data-ttu-id="da0a9-390">.NET Framework 4.7.1 および Visual Studio 2017 バージョン 15.3 以降では、ASP.NET によって、ASP.NET Web コントロールによる Visual Studio のアクセシビリティ テクノロジの処理方法が向上しています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-390">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="da0a9-391">主な変更点は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da0a9-391">Changes include the following:</span></span>

- <span data-ttu-id="da0a9-392">**[詳細の表示]** ウィザードの **[フィールドの追加]** ダイアログや **ListView** ウィザードの **[ListView の構成]** ダイアログなど、コントロールで不足していた UI アクセシビリティ パターンを実装するための変更。</span><span class="sxs-lookup"><span data-stu-id="da0a9-392">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="da0a9-393">**データ ページャー フィールド エディター**など、ハイ コントラスト モードでの表示を改善するための変更。</span><span class="sxs-lookup"><span data-stu-id="da0a9-393">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="da0a9-394">DataPager コントロールの **[ページャーのフィールドを編集]** ウィザードの **[フィールド]** ダイアログ、 **[ObjectContext の構成]** ダイアログ、 **[データ ソースの構成]** ウィザードの **[データの選択の構成]** ダイアログなど、キーボードの操作性を改善するための変更。</span><span class="sxs-lookup"><span data-stu-id="da0a9-394">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="da0a9-395">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="da0a9-395">.NET SDK Tools</span></span>

<span data-ttu-id="da0a9-396">[構成エディター ツール (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) および[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) が、さまざまなアクセシビリティの問題を修正して改善されています。</span><span class="sxs-lookup"><span data-stu-id="da0a9-396">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="da0a9-397">その問題のほとんどは、名前の未定義や、特定の UI の自動化パターンが正しく実装されていないといった軽微なものです。</span><span class="sxs-lookup"><span data-stu-id="da0a9-397">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="da0a9-398">このような問題は、多くのユーザーが認識しないものですが、スクリーン リーダーのような支援技術を使用するお客様はこれらの SDK ツールのアクセシビリティの強化を実感されるでしょう。</span><span class="sxs-lookup"><span data-stu-id="da0a9-398">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="da0a9-399">これらの機能強化により、キーボード フォーカスの順序など、以前のいくつかの動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-399">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="da0a9-400">Windows Workflow Foundation (WF) ワークフロー デザイナー</span><span class="sxs-lookup"><span data-stu-id="da0a9-400">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="da0a9-401">ワークフロー デザイナーでのアクセシビリティに関する変更は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da0a9-401">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="da0a9-402">一部のコントロールで、タブ オーダーが左から右、上から下に変更されます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-402">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="da0a9-403"><xref:System.ServiceModel.Activities.InitializeCorrelation> アクティビティの関連付けデータを設定するための関連付けの初期化ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-403">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="da0a9-404"><xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティのコンテンツ定義ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-404">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="da0a9-405">キーボードで利用できる機能が増えます:</span><span class="sxs-lookup"><span data-stu-id="da0a9-405">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="da0a9-406">アクティビティのプロパティを編集する際、プロパティ グループに初めてフォーカスを設定したときに、プロパティ グループをキーボードで折りたたむことができます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-406">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="da0a9-407">警告アイコンにキーボードでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-407">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="da0a9-408">**[プロパティ]** ウィンドウの **[その他のプロパティ]** ボタンに、キーボードでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-408">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="da0a9-409">キーボードを使って、ワークフロー デザイナーの **[引数]** および **[変数]** ウィンドウのヘッダー項目にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="da0a9-409">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="da0a9-410">次のような場合に、フォーカスのある項目の可視性が向上しました:</span><span class="sxs-lookup"><span data-stu-id="da0a9-410">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="da0a9-411">ワークフロー デザイナーおよびアクティビティ デザイナーで使われているデータ グリッドへの行の追加。</span><span class="sxs-lookup"><span data-stu-id="da0a9-411">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="da0a9-412"><xref:System.ServiceModel.Activities.ReceiveReply> および <xref:System.ServiceModel.Activities.SendReply> アクティビティ内のフィールド間の Tab 移動。</span><span class="sxs-lookup"><span data-stu-id="da0a9-412">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="da0a9-413">変数または引数の既定値の設定</span><span class="sxs-lookup"><span data-stu-id="da0a9-413">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="da0a9-414">スクリーン リーダーが正しく認識できるようになりました:</span><span class="sxs-lookup"><span data-stu-id="da0a9-414">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="da0a9-415">ワークフロー デザイナーで設定されたブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="da0a9-415">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="da0a9-416"><xref:System.Activities.Statements.FlowSwitch%601>、<xref:System.Activities.Statements.FlowDecision>、<xref:System.ServiceModel.Activities.CorrelationScope> アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-416">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="da0a9-417"><xref:System.ServiceModel.Activities.Receive> アクティビティの内容。</span><span class="sxs-lookup"><span data-stu-id="da0a9-417">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="da0a9-418"><xref:System.Activities.Statements.InvokeMethod> アクティビティのターゲットの種類。</span><span class="sxs-lookup"><span data-stu-id="da0a9-418">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="da0a9-419"><xref:System.Activities.Statements.TryCatch> アクティビティの [例外] コンボ ボックスと [Finally] セクション。</span><span class="sxs-lookup"><span data-stu-id="da0a9-419">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="da0a9-420">メッセージング アクティビティの [メッセージの種類] コンボ ボックス、[関連付け初期化子の追加] ウィンドウのスプリッター、[コンテンツ定義] ウィンドウで、および [CorrelatesOn の定義] ウィンドウ (<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply>)。</span><span class="sxs-lookup"><span data-stu-id="da0a9-420">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="da0a9-421">ステート マシンの遷移と遷移先。</span><span class="sxs-lookup"><span data-stu-id="da0a9-421">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="da0a9-422"><xref:System.Activities.Statements.FlowDecision> アクティビティの注釈とコネクタ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-422">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="da0a9-423">アクティビティのコンテキスト (右クリック) メニュー。</span><span class="sxs-lookup"><span data-stu-id="da0a9-423">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="da0a9-424">プロパティ グリッドの、プロパティ値エディター、[検索のクリア] ボタン、[カテゴリ別] および [アルファベット順] の並べ替えボタン、[式エディター] ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-424">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="da0a9-425">ワークフロー デザイナーのズーム パーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-425">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="da0a9-426"><xref:System.Activities.Statements.Parallel> および <xref:System.Activities.Statements.Pick> アクティビティの区切り記号。</span><span class="sxs-lookup"><span data-stu-id="da0a9-426">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="da0a9-427"><xref:System.Activities.Statements.InvokeDelegate> アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-427">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="da0a9-428">ディクショナリ アクティビティの [型の選択] ウィンドウ (`Microsoft.Activities.AddToDictionary<TKey,TValue>`、`Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` など)。</span><span class="sxs-lookup"><span data-stu-id="da0a9-428">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="da0a9-429">[.NET 型の参照と選択] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="da0a9-429">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="da0a9-430">ワークフロー デザイナーでの階層リンク。</span><span class="sxs-lookup"><span data-stu-id="da0a9-430">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="da0a9-431">ハイ コントラスト テーマを選ぶと、要素間のコントラスト比の向上や、フォーカス要素に使われる選択ボックスの認識性の向上など、ワークフロー デザイナーとそのコントロールの表示について多くの点が向上していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="da0a9-431">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="da0a9-432">参照</span><span class="sxs-lookup"><span data-stu-id="da0a9-432">See also</span></span>

- [<span data-ttu-id="da0a9-433">.NET Framework の新機能</span><span class="sxs-lookup"><span data-stu-id="da0a9-433">What's new in the .NET Framework</span></span>](index.md)
