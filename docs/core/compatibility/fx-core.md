---
title: 破壊的変更 - .NET Framework から .NET Core
description: .NET Framework から .NET Core への破壊的変更を一覧表示します。
ms.date: 12/18/2019
ms.openlocfilehash: 6959bffab62cabc524062231db989de45c8c1498
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116488"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="eb113-103">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="eb113-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="eb113-104">.NET Framework から .NET Core にアプリを移行する場合、この記事の一覧にある破壊的変更による影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb113-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="eb113-105">破壊的変更はカテゴリ別に分類され、そのカテゴリ内では、導入された .NET Core のバージョンによってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="eb113-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core they were introduced in.</span></span>

> [!NOTE]
> <span data-ttu-id="eb113-106">この記事は、.NET Framework と .NET Core の間の破壊的変更の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="eb113-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="eb113-107">最も重要な破壊的変更が認識されると、こちらに追加されます。</span><span class="sxs-lookup"><span data-stu-id="eb113-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="eb113-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="eb113-108">CoreFx</span></span>

- [<span data-ttu-id="eb113-109">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="eb113-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)

### <a name="net-core-21"></a><span data-ttu-id="eb113-110">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="eb113-110">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="eb113-111">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="eb113-111">Windows Forms</span></span>

<span data-ttu-id="eb113-112">Windows フォームのサポートは、.NET Core にバージョン 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="eb113-112">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="eb113-113">.NET Framework から .NET Core に Windows フォーム アプリを移行する場合、アプリがこの記事の一覧にある破壊的変更による影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb113-113">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="eb113-114">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="eb113-114">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="eb113-115">ヒントが表示されていると CellFormatting が発生しない</span><span class="sxs-lookup"><span data-stu-id="eb113-115">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="eb113-116">Control.DefaultFont を Segoe UI 9 pt に変更</span><span class="sxs-lookup"><span data-stu-id="eb113-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="eb113-117">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="eb113-117">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="eb113-118">一部の Windows フォーム型から SerializableAttribute を削除</span><span class="sxs-lookup"><span data-stu-id="eb113-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="eb113-119">AllowUpdateChildControlIndexForTabControls 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-119">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-120">DomainUpDown.UseLegacyScrolling 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-120">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-121">DoNotLoadLatestRichEditControl 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-121">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-122">DoNotSupportSelectAllShortcutInMultilineTextBox 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-122">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-123">DontSupportReentrantFilterMessage 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-123">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-124">EnableVisualStyleValidation 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-124">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-125">UseLegacyContextMenuStripSourceControlValue 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-125">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-126">UseLegacyImages 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="eb113-126">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="eb113-127">AccessibleObject.RuntimeIDFirstItem のアクセスに対する変更</span><span class="sxs-lookup"><span data-stu-id="eb113-127">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="eb113-128">Windows フォームからの重複する API の削除</span><span class="sxs-lookup"><span data-stu-id="eb113-128">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="eb113-129">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="eb113-129">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="eb113-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="eb113-130">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="eb113-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb113-131">See also</span></span>

- [<span data-ttu-id="eb113-132">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="eb113-132">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="eb113-133">.NET Core で使用できない .NET Framework テクノロジ</span><span class="sxs-lookup"><span data-stu-id="eb113-133">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
