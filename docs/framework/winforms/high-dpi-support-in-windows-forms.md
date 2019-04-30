---
title: Windows フォームで高 DPI のサポート
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1641702c7b1c3d3b0e83c59a96529de70f699d17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966947"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="1b9ad-102">Windows フォームで高 DPI のサポート</span><span class="sxs-lookup"><span data-stu-id="1b9ad-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="1b9ad-103">以降、.NET Framework 4.7 では、Windows フォームには、共通の高 DPI および動的 DPI シナリオの機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="1b9ad-104">不足している機能には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-104">These include:</span></span>

- <span data-ttu-id="1b9ad-105">スケーリングとさまざまな Windows フォームのレイアウトの機能強化を制御するなど、<xref:System.Windows.Forms.MonthCalendar>コントロールと<xref:System.Windows.Forms.CheckedListBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="1b9ad-106">単一パスをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-106">Single-pass scaling.</span></span>  <span data-ttu-id="1b9ad-107">.NET Framework 4.6 以前のバージョンで、スケーリングが必要以上にスケールする一部のコントロールの原因とする複数のパスから実行されました。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="1b9ad-108">Windows フォーム アプリケーションが起動された後に、ユーザー、DPI またはスケール ファクターを変更、動的 DPI シナリオのサポート。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="1b9ad-109">.NET Framework 4.7 以降では、.NET Framework のバージョンでは、高 DPI サポートの強化は、オプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="1b9ad-110">これを活用するためにアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="1b9ad-111">高 DPI のサポートを Windows フォーム アプリの構成</span><span class="sxs-lookup"><span data-stu-id="1b9ad-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="1b9ad-112">高 DPI 対応をサポートする Windows フォームの新しい機能は、.NET Framework 4.7 を対象し、Windows 10 Creators Update 以降の Windows オペレーティング システムで実行しているアプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="1b9ad-113">さらに、Windows フォーム アプリケーションで高 DPI のサポートを構成するにする必要があります、次のように行います。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="1b9ad-114">Windows 10 と互換性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="1b9ad-115">これを行うには、マニフェスト ファイルに、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="1b9ad-116">モニターごとの DPI 認識を有効にする、 *app.config*ファイル。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="1b9ad-117">Windows フォームが導入されていますが、新しい[ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../configure-apps/file-schema/winforms/index.md)の新機能と .NET Framework 4.7 以降では追加のカスタマイズをサポートする要素。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="1b9ad-118">高 DPI をサポートする新しい機能を利用するには、アプリケーション構成ファイルに、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="1b9ad-119">.NET Framework の以前のバージョンでは、マニフェストを使用して、高 DPI のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="1b9ad-120">このアプローチは推奨されなく app.config ファイルで定義された設定をオーバーライドするためです。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="1b9ad-121">呼び出す静的<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="1b9ad-122">これは、アプリケーションのエントリ ポイントでは、最初のメソッド呼び出しでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="1b9ad-123">例えば:</span><span class="sxs-lookup"><span data-stu-id="1b9ad-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="1b9ad-124">個々 の高 DPI 機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="1b9ad-125">設定、`DpiAwareness`値を`PerMonitorV2`.NET Framework 4.7 以降では .NET Framework のバージョンでサポートされている、すべての高 DPI 認識の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="1b9ad-126">通常、これは、ほとんどの Windows フォーム アプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="1b9ad-127">ただし、1 つまたは複数の個々 の機能を無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="1b9ad-128">これを行うための最も重要な理由は、既存のアプリケーション コードは、その機能を既に処理です。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="1b9ad-129">たとえば、アプリケーションでは、自動スケーリングを処理する場合は次のように、自動サイズ変更機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="1b9ad-130">個々 のキーおよび値の一覧は、次を参照してください。 [Windows フォームの追加の構成要素](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="1b9ad-131">新しい DPI 変更イベント</span><span class="sxs-lookup"><span data-stu-id="1b9ad-131">New DPI change events</span></span>

<span data-ttu-id="1b9ad-132">3 つの新しいイベントは、.NET Framework 4.7 以降では、プログラムによって動的 DPI の変更を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="1b9ad-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>を親コントロールの DPI 変更イベントの後に、コントロールの DPI 設定がプログラムで変更またはフォームが発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="1b9ad-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>を親コントロールの DPI 変更イベントの前に、コントロールの DPI 設定がプログラムで変更またはフォームが発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="1b9ad-135"><xref:System.Windows.Forms.Form.DpiChanged>、フォームが現在表示されているディスプレイ デバイスの DPI 設定が変更されたときに、これが発生します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="1b9ad-136">新しいヘルパー メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="1b9ad-136">New helper methods and properties</span></span>

<span data-ttu-id="1b9ad-137">.NET Framework 4.7 では、さまざまな DPI スケールに関する情報を提供し、DPI スケールを実行できるようにする新しいヘルパー メソッドとプロパティも追加します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="1b9ad-138">不足している機能には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-138">These include:</span></span>

- <span data-ttu-id="1b9ad-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>を論理座標から値をデバイス ピクセルに変換します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="1b9ad-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>、ビットマップ イメージにデバイスの論理 DPI スケールします。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="1b9ad-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>を現在のデバイスの DPI が返されます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="1b9ad-142">バージョン管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1b9ad-142">Versioning considerations</span></span>

<span data-ttu-id="1b9ad-143">.NET Framework 4.7 と Windows 10 Creators Update でを実行するだけでなく、アプリケーションもない高 DPI 機能強化と互換性のある環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="1b9ad-144">この場合、代替のアプリケーションを開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="1b9ad-145">実行するために行うことができます[カスタム描画](./controls/user-drawn-controls.md)スケーリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="1b9ad-146">これを行うには、アプリが実行されているオペレーティング システムを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="1b9ad-147">次のようなコードで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="1b9ad-148">エントリのアプリケーション マニフェストでサポートされているオペレーティング システムとして表示されていない場合、アプリケーションはありません Windows 10 が検出が正常に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="1b9ad-149">アプリケーションがビルドされた .NET Framework のバージョンをチェックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="1b9ad-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b9ad-150">See also</span></span>

- [<span data-ttu-id="1b9ad-151">Windows フォームの構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b9ad-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="1b9ad-152">Windows フォームのサイズとスケールを調整する</span><span class="sxs-lookup"><span data-stu-id="1b9ad-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
