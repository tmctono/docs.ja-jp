---
title: Windows フォームに関する破壊的変更
description: .NET Core および .NET 5 の Windows フォームにおける破壊的変更の一覧を示します。
ms.date: 09/08/2020
ms.openlocfilehash: 2311faab026bf1dfde348e231937eff73ec46172
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804863"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="99646-103">Windows フォームでの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="99646-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="99646-104">Windows フォームのサポートは、.NET Core にバージョン 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="99646-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="99646-105">この記事では、Windows フォームの破壊的変更を、導入された .NET のバージョン別に説明します。</span><span class="sxs-lookup"><span data-stu-id="99646-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="99646-106">この記事は、.NET Framework または以前のバージョンの .NET Core (3.0 以降) から Windows フォーム アプリをアップグレードするユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="99646-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="99646-107">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="99646-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="99646-108">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="99646-108">Breaking change</span></span> | <span data-ttu-id="99646-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="99646-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="99646-110">カスタマイズされたセル スタイルのフォントが DataGridView によってリセットされなくなった</span><span class="sxs-lookup"><span data-stu-id="99646-110">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="99646-111">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-111">5.0</span></span> |
| [<span data-ttu-id="99646-112">WPF アプリと WinForms アプリで OutputType が WinExe に設定されている</span><span class="sxs-lookup"><span data-stu-id="99646-112">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="99646-113">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-113">5.0</span></span> |
| [<span data-ttu-id="99646-114">DataGridView 関連の API が InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="99646-114">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="99646-115">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-115">5.0</span></span> |
| [<span data-ttu-id="99646-116">WinForms と WPF アプリで Microsoft.NET.Sdk が使用される</span><span class="sxs-lookup"><span data-stu-id="99646-116">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="99646-117">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-117">5.0</span></span> |
| [<span data-ttu-id="99646-118">削除されたステータス バー コントロール</span><span class="sxs-lookup"><span data-stu-id="99646-118">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="99646-119">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-119">5.0</span></span> |
| [<span data-ttu-id="99646-120">WinForms メソッドで ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="99646-120">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="99646-121">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-121">5.0</span></span> |
| [<span data-ttu-id="99646-122">WinForms メソッドで ArgumentNullException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="99646-122">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="99646-123">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-123">5.0</span></span> |
| [<span data-ttu-id="99646-124">WinForms プロパティによる ArgumentOutOfRangeException のスロー</span><span class="sxs-lookup"><span data-stu-id="99646-124">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="99646-125">5.0</span><span class="sxs-lookup"><span data-stu-id="99646-125">5.0</span></span> |
| [<span data-ttu-id="99646-126">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="99646-126">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="99646-127">3.1</span><span class="sxs-lookup"><span data-stu-id="99646-127">3.1</span></span> |
| [<span data-ttu-id="99646-128">ヒントが表示されていると CellFormatting が発生しない</span><span class="sxs-lookup"><span data-stu-id="99646-128">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="99646-129">3.1</span><span class="sxs-lookup"><span data-stu-id="99646-129">3.1</span></span> |
| [<span data-ttu-id="99646-130">Control.DefaultFont を Segoe UI 9 pt に変更</span><span class="sxs-lookup"><span data-stu-id="99646-130">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="99646-131">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-131">3.0</span></span> |
| [<span data-ttu-id="99646-132">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="99646-132">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="99646-133">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-133">3.0</span></span> |
| [<span data-ttu-id="99646-134">一部の Windows フォーム型から SerializableAttribute を削除</span><span class="sxs-lookup"><span data-stu-id="99646-134">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="99646-135">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-135">3.0</span></span> |
| [<span data-ttu-id="99646-136">AllowUpdateChildControlIndexForTabControls 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-136">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="99646-137">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-137">3.0</span></span> |
| [<span data-ttu-id="99646-138">DomainUpDown.UseLegacyScrolling 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-138">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="99646-139">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-139">3.0</span></span> |
| [<span data-ttu-id="99646-140">DoNotLoadLatestRichEditControl 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-140">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="99646-141">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-141">3.0</span></span> |
| [<span data-ttu-id="99646-142">DoNotSupportSelectAllShortcutInMultilineTextBox 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-142">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="99646-143">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-143">3.0</span></span> |
| [<span data-ttu-id="99646-144">DontSupportReentrantFilterMessage 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-144">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="99646-145">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-145">3.0</span></span> |
| [<span data-ttu-id="99646-146">EnableVisualStyleValidation 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-146">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="99646-147">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-147">3.0</span></span> |
| [<span data-ttu-id="99646-148">UseLegacyContextMenuStripSourceControlValue 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-148">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="99646-149">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-149">3.0</span></span> |
| [<span data-ttu-id="99646-150">UseLegacyImages 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="99646-150">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="99646-151">3.0</span><span class="sxs-lookup"><span data-stu-id="99646-151">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="99646-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="99646-152">.NET 5.0</span></span>

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

***

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="99646-153">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="99646-153">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="99646-154">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="99646-154">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="99646-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="99646-155">See also</span></span>

- [<span data-ttu-id="99646-156">Windows フォーム アプリを .NET Core に移植する</span><span class="sxs-lookup"><span data-stu-id="99646-156">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
