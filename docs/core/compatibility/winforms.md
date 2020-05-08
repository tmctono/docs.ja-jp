---
title: Windows フォームに関する破壊的変更
description: .NET Core 用の Windows フォームにおける破壊的変更の一覧を示します。
ms.date: 01/08/2020
ms.openlocfilehash: 75d369c7fb999da81a50fe46716e125c3840eb7a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158438"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="a0fca-103">Windows フォームでの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="a0fca-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="a0fca-104">Windows フォームのサポートは、.NET Core にバージョン 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="a0fca-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="a0fca-105">この記事では、Windows フォームの破壊的変更を、導入された .NET Core のバージョン別に説明します。</span><span class="sxs-lookup"><span data-stu-id="a0fca-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="a0fca-106">.NET Framework または以前のバージョンの .NET Core (3.0 以降) から Windows フォーム アプリをアップグレードする場合は、この記事が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0fca-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="a0fca-107">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0fca-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a0fca-108">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="a0fca-108">Breaking change</span></span> | <span data-ttu-id="a0fca-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a0fca-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a0fca-110">削除されたステータス バー コントロール</span><span class="sxs-lookup"><span data-stu-id="a0fca-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="a0fca-111">5.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-111">5.0</span></span> |
| [<span data-ttu-id="a0fca-112">WinForms メソッドで ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="a0fca-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="a0fca-113">5.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-113">5.0</span></span> |
| [<span data-ttu-id="a0fca-114">WinForms メソッドで ArgumentNullException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="a0fca-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="a0fca-115">5.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-115">5.0</span></span> |
| [<span data-ttu-id="a0fca-116">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="a0fca-116">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="a0fca-117">3.1</span><span class="sxs-lookup"><span data-stu-id="a0fca-117">3.1</span></span> |
| [<span data-ttu-id="a0fca-118">ヒントが表示されていると CellFormatting が発生しない</span><span class="sxs-lookup"><span data-stu-id="a0fca-118">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="a0fca-119">3.1</span><span class="sxs-lookup"><span data-stu-id="a0fca-119">3.1</span></span> |
| [<span data-ttu-id="a0fca-120">Control.DefaultFont を Segoe UI 9 pt に変更</span><span class="sxs-lookup"><span data-stu-id="a0fca-120">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="a0fca-121">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-121">3.0</span></span> |
| [<span data-ttu-id="a0fca-122">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="a0fca-122">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="a0fca-123">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-123">3.0</span></span> |
| [<span data-ttu-id="a0fca-124">一部の Windows フォーム型から SerializableAttribute を削除</span><span class="sxs-lookup"><span data-stu-id="a0fca-124">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="a0fca-125">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-125">3.0</span></span> |
| [<span data-ttu-id="a0fca-126">AllowUpdateChildControlIndexForTabControls 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-126">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-127">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-127">3.0</span></span> |
| [<span data-ttu-id="a0fca-128">DomainUpDown.UseLegacyScrolling 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-128">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-129">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-129">3.0</span></span> |
| [<span data-ttu-id="a0fca-130">DoNotLoadLatestRichEditControl 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-130">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-131">3.0</span></span> |
| [<span data-ttu-id="a0fca-132">DoNotSupportSelectAllShortcutInMultilineTextBox 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-132">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-133">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-133">3.0</span></span> |
| [<span data-ttu-id="a0fca-134">DontSupportReentrantFilterMessage 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-134">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-135">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-135">3.0</span></span> |
| [<span data-ttu-id="a0fca-136">EnableVisualStyleValidation 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-136">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-137">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-137">3.0</span></span> |
| [<span data-ttu-id="a0fca-138">UseLegacyContextMenuStripSourceControlValue 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-138">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-139">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-139">3.0</span></span> |
| [<span data-ttu-id="a0fca-140">UseLegacyImages 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="a0fca-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="a0fca-141">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-141">3.0</span></span> |
| [<span data-ttu-id="a0fca-142">AccessibleObject.RuntimeIDFirstItem のアクセスに対する変更</span><span class="sxs-lookup"><span data-stu-id="a0fca-142">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="a0fca-143">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-143">3.0</span></span> |
| [<span data-ttu-id="a0fca-144">Windows フォームからの重複する API の削除</span><span class="sxs-lookup"><span data-stu-id="a0fca-144">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="a0fca-145">3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-145">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="a0fca-146">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-146">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="a0fca-147">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a0fca-147">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="a0fca-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a0fca-148">.NET Core 3.0</span></span>

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

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="a0fca-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0fca-149">See also</span></span>

- [<span data-ttu-id="a0fca-150">Windows フォーム アプリを .NET Core に移植する</span><span class="sxs-lookup"><span data-stu-id="a0fca-150">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
