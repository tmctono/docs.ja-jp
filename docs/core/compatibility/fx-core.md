---
title: 破壊的変更 - .NET Framework から .NET Core
titleSuffix: ''
description: .NET Framework から .NET Core への破壊的変更を一覧表示します。
ms.date: 05/05/2020
ms.openlocfilehash: e9fa37dba89bbd6c4829614c27cb66206069fa9b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414457"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="367bb-103">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="367bb-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="367bb-104">.NET Framework から .NET Core にアプリを移行する場合、この記事の一覧にある破壊的変更による影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="367bb-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="367bb-105">破壊的変更はカテゴリ別に分類され、そのカテゴリ内では、導入された .NET Core のバージョンによってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="367bb-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="367bb-106">この記事は、.NET Framework と .NET Core の間の破壊的変更の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="367bb-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="367bb-107">最も重要な破壊的変更が認識されると、こちらに追加されます。</span><span class="sxs-lookup"><span data-stu-id="367bb-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="367bb-108">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="367bb-108">Core .NET libraries</span></span>

- [<span data-ttu-id="367bb-109">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="367bb-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="367bb-110">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="367bb-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="367bb-111">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="367bb-112">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="367bb-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)
- [<span data-ttu-id="367bb-113">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="367bb-113">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a><span data-ttu-id="367bb-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="367bb-114">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="367bb-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="367bb-115">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a><span data-ttu-id="367bb-116">暗号</span><span class="sxs-lookup"><span data-stu-id="367bb-116">Cryptography</span></span>

- [<span data-ttu-id="367bb-117">SignedCms.ComputeSignature のブール型パラメーターの尊重</span><span class="sxs-lookup"><span data-stu-id="367bb-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="367bb-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="367bb-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a><span data-ttu-id="367bb-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="367bb-119">MSBuild</span></span>

- [<span data-ttu-id="367bb-120">リソース マニフェストのファイル名の変更</span><span class="sxs-lookup"><span data-stu-id="367bb-120">Resource manifest file name change</span></span>](#resource-manifest-file-name-change)

### <a name="net-core-30"></a><span data-ttu-id="367bb-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="367bb-121">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a><span data-ttu-id="367bb-122">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="367bb-122">Networking</span></span>

- [<span data-ttu-id="367bb-123">WebClient.CancelAsync がすぐにキャンセルされない場合がある</span><span class="sxs-lookup"><span data-stu-id="367bb-123">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately)
- [<span data-ttu-id="367bb-124">現在、Cookie パスの処理は、RFC 6265 に準拠している</span><span class="sxs-lookup"><span data-stu-id="367bb-124">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265)

### <a name="net-core-20"></a><span data-ttu-id="367bb-125">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="367bb-125">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

### <a name="net-50"></a><span data-ttu-id="367bb-126">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="367bb-126">.NET 5.0</span></span>

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="367bb-127">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="367bb-127">Windows Forms</span></span>

<span data-ttu-id="367bb-128">Windows フォームのサポートは、.NET Core にバージョン 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="367bb-128">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="367bb-129">.NET Framework から .NET Core に Windows フォーム アプリを移行する場合、アプリがこの記事の一覧にある破壊的変更による影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="367bb-129">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="367bb-130">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="367bb-130">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="367bb-131">ヒントが表示されていると CellFormatting が発生しない</span><span class="sxs-lookup"><span data-stu-id="367bb-131">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="367bb-132">Control.DefaultFont を Segoe UI 9 pt に変更</span><span class="sxs-lookup"><span data-stu-id="367bb-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="367bb-133">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="367bb-133">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="367bb-134">一部の Windows フォーム型から SerializableAttribute を削除</span><span class="sxs-lookup"><span data-stu-id="367bb-134">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="367bb-135">AllowUpdateChildControlIndexForTabControls 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-135">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-136">DomainUpDown.UseLegacyScrolling 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-136">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-137">DoNotLoadLatestRichEditControl 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-137">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-138">DoNotSupportSelectAllShortcutInMultilineTextBox 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-138">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-139">DontSupportReentrantFilterMessage 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-139">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-140">EnableVisualStyleValidation 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-140">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-141">UseLegacyContextMenuStripSourceControlValue 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-141">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="367bb-142">UseLegacyImages 互換性スイッチがサポートされない</span><span class="sxs-lookup"><span data-stu-id="367bb-142">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a><span data-ttu-id="367bb-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="367bb-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="367bb-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="367bb-144">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="367bb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="367bb-145">See also</span></span>

- [<span data-ttu-id="367bb-146">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="367bb-146">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="367bb-147">.NET Core で使用できない .NET Framework テクノロジ</span><span class="sxs-lookup"><span data-stu-id="367bb-147">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
