---
title: .NET Core 3.1 の新機能
description: .NET Core 3.1 の新機能について説明します。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 0905cbebb2d966570be4ac3aefb40f4377b97061
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742577"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="5dc47-103">.NET Core 3.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="5dc47-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="5dc47-104">この記事では、.NET Core 3.1 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="5dc47-105">このリリースには、小規模であるが重要な修正に重点を置いた .NET Core 3.0 のマイナー機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="5dc47-106">.NET Core 3.1 に関する最も重要な機能は、[長期的なサポート (LTS)](#long-term-support) リリースであるということです。</span><span class="sxs-lookup"><span data-stu-id="5dc47-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="5dc47-107">Visual Studio 2019 を使用している場合は、.NET Core 3.1 プロジェクトを操作するために [Visual Studio 2019 バージョン 16.4](https://visualstudio.microsoft.com/downloads/) に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="5dc47-108">Visual Studio の新機能の詳細については、「[Visual Studio 2019 バージョン 16.4 の新機能](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-108">For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="5dc47-109">Visual Studio for Mac でも .NET Core 3.1 がサポートされており、Visual Studio for Mac 8.4 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="5dc47-110">リリースの詳細については、「[.NET Core 3.1 についてのお知らせ](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="5dc47-111">Windows、macOS、または Linux 上に [.NET Core 3.1 をダウンロードして使い始めましょう](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="5dc47-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="5dc47-112">長期的なサポート</span><span class="sxs-lookup"><span data-stu-id="5dc47-112">Long-term support</span></span>

<span data-ttu-id="5dc47-113">.NET Core 3.1 は、次の 3 年間にわたって Microsoft のサポートが提供される LTS リリースです。</span><span class="sxs-lookup"><span data-stu-id="5dc47-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="5dc47-114">アプリを .NET Core 3.1 に移行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="5dc47-115">他のメジャー リリースの現在のライフサイクルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5dc47-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="5dc47-116">解放</span><span class="sxs-lookup"><span data-stu-id="5dc47-116">Release</span></span> | <span data-ttu-id="5dc47-117">メモ</span><span class="sxs-lookup"><span data-stu-id="5dc47-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="5dc47-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5dc47-118">.NET Core 3.0</span></span> | <span data-ttu-id="5dc47-119">2020 年 3 月 3 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="5dc47-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5dc47-120">.NET Core 2.2</span></span> | <span data-ttu-id="5dc47-121">2019 年 12 月 23 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="5dc47-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5dc47-122">.NET Core 2.1</span></span> | <span data-ttu-id="5dc47-123">2021 年 8 月 21 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="5dc47-124">詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="5dc47-125">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="5dc47-125">Windows Forms</span></span>

<span data-ttu-id="5dc47-126">*Windows のみ*</span><span class="sxs-lookup"><span data-stu-id="5dc47-126">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="5dc47-127">Windows フォームで破壊的変更が行われています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-127">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="5dc47-128">Windows フォームには、Visual Studio Designer Toolbox でしばらくの間利用できなくなっているレガシ コントロールが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="5dc47-128">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="5dc47-129">これらは、.NET Framework 2.0 の新しいコントロールに置き換えられていました。</span><span class="sxs-lookup"><span data-stu-id="5dc47-129">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="5dc47-130">これらは、Desktop SDK for .NET Core 3.1. から削除されています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-130">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="5dc47-131">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="5dc47-131">Removed control</span></span> | <span data-ttu-id="5dc47-132">推奨代替</span><span class="sxs-lookup"><span data-stu-id="5dc47-132">Recommended replacement</span></span> | <span data-ttu-id="5dc47-133">削除された関連 API</span><span class="sxs-lookup"><span data-stu-id="5dc47-133">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="5dc47-134">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5dc47-134">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="5dc47-135">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="5dc47-135">DataGridCell</span></span><br/><span data-ttu-id="5dc47-136">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="5dc47-136">DataGridRow</span></span><br/><span data-ttu-id="5dc47-137">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="5dc47-137">DataGridTableCollection</span></span><br/><span data-ttu-id="5dc47-138">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="5dc47-138">DataGridColumnCollection</span></span><br/><span data-ttu-id="5dc47-139">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="5dc47-139">DataGridTableStyle</span></span><br/><span data-ttu-id="5dc47-140">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="5dc47-140">DataGridColumnStyle</span></span><br/><span data-ttu-id="5dc47-141">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="5dc47-141">DataGridLineStyle</span></span><br/><span data-ttu-id="5dc47-142">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="5dc47-142">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="5dc47-143">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="5dc47-143">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="5dc47-144">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="5dc47-144">DataGridBoolColumn</span></span><br/><span data-ttu-id="5dc47-145">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="5dc47-145">DataGridTextBox</span></span><br/><span data-ttu-id="5dc47-146">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="5dc47-146">GridColumnStylesCollection</span></span><br/><span data-ttu-id="5dc47-147">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="5dc47-147">GridTableStylesCollection</span></span><br/><span data-ttu-id="5dc47-148">HitTestType</span><span class="sxs-lookup"><span data-stu-id="5dc47-148">HitTestType</span></span> |
| <span data-ttu-id="5dc47-149">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5dc47-149">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="5dc47-150">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="5dc47-150">ToolBarAppearance</span></span> |
| <span data-ttu-id="5dc47-151">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="5dc47-151">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="5dc47-152">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="5dc47-152">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="5dc47-153">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="5dc47-153">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="5dc47-154">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="5dc47-154">ToolBarButtonStyle</span></span><br/><span data-ttu-id="5dc47-155">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="5dc47-155">ToolBarTextAlign</span></span> |
| <span data-ttu-id="5dc47-156">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5dc47-156">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="5dc47-157">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="5dc47-157">MenuItemCollection</span></span> |
| <span data-ttu-id="5dc47-158">MainMenu</span><span class="sxs-lookup"><span data-stu-id="5dc47-158">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="5dc47-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5dc47-159">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="5dc47-160">アプリケーションを .NET Core 3.1 に更新し、コントロールの置き換えを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-160">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="5dc47-161">コントロールの置き換えは、基本的には型の "検索と置換" という単純なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5dc47-161">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="5dc47-162">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="5dc47-162">C++/CLI</span></span>

<span data-ttu-id="5dc47-163">*Windows のみ*</span><span class="sxs-lookup"><span data-stu-id="5dc47-163">*Windows only*</span></span>

<span data-ttu-id="5dc47-164">C++/CLI (別名 "マネージド C++") プロジェクトを作成するためのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-164">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="5dc47-165">これらのプロジェクトから生成されるバイナリは、.NET Core 3.0 以降のバージョンと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-165">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="5dc47-166">Visual Studio 2019 バージョン 16.4 に C++/CLI のサポートを追加するには、[C++ ワークロードを使用するデスクトップ開発](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-166">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="5dc47-167">このワークロードによって、次の 2 つのテンプレートが Visual Studio に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-167">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="5dc47-168">CLR クラス ライブラリ (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="5dc47-168">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="5dc47-169">CLR 空のプロジェクト (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="5dc47-169">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dc47-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="5dc47-170">Next steps</span></span>

- [<span data-ttu-id="5dc47-171">.NET Core 3.0 と 3.1 の間の破壊的変更を確認する</span><span class="sxs-lookup"><span data-stu-id="5dc47-171">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="5dc47-172">Windows フォーム アプリ用の .NET Core 3.1 における破壊的変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-172">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
