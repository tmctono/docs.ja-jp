---
title: 破壊的変更、.NET Framework から .NET Core 3.0 - .NET Core
description: .NET Framework から .NET Core 3.0 への Windows フォームと Windows Presentation Foundation の破壊的変更の一覧を示します。
ms.date: 09/10/2019
ms.openlocfilehash: a374e35192c7aad07e986e0e0b75039642744edc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089573"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="95c4c-103">.NET Framework から .NET Core 3.0 への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="95c4c-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95c4c-104">この記事は作成中です。</span><span class="sxs-lookup"><span data-stu-id="95c4c-104">This article is under construction.</span></span> <span data-ttu-id="95c4c-105">これは、.NET Core の破壊的変更の完全なリストではありません。</span><span class="sxs-lookup"><span data-stu-id="95c4c-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="95c4c-106">.NET Core の破壊的変更の詳細については、GitHub の dotnet/docs リポジトリで個別の[破壊的変更の問題](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)について調べてください。</span><span class="sxs-lookup"><span data-stu-id="95c4c-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="95c4c-107">.NET Framework から .NET Core 3.0 に Windows フォームまたは Windows Presentation Foundation のアプリケーションを移行する場合、ご使用のアプリに影響する可能性がある破壊的変更について次のトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="95c4c-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="95c4c-108">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="95c4c-108">Windows Forms</span></span>

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
