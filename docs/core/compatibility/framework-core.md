---
title: 破壊的変更、.NET Framework から .NET Core 3.0 - .NET Core
description: .NET Framework から .NET Core 3.0 への Windows フォームと Windows Presentation Foundation の破壊的変更の一覧を示します。
ms.date: 09/10/2019
ms.openlocfilehash: 80c93dd7a8715a9bcc6d81605ffe5af4b0461257
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739440"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="0a123-103">.NET Framework から .NET Core 3.0 への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="0a123-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

<span data-ttu-id="0a123-104">.NET Framework から .NET Core 3.0 に Windows フォームまたは Windows Presentation Foundation のアプリケーションを移行する場合、ご使用のアプリに影響する可能性がある破壊的変更について次のトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a123-104">If you're migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="0a123-105">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="0a123-105">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
