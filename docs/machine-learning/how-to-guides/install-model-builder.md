---
title: モデル ビルダーのインストール方法
description: ML.NET モデル ビルダー ツールのインストール方法について説明します
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306324"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="49f94-103">ML.NET モデル ビルダーのインストール方法</span><span class="sxs-lookup"><span data-stu-id="49f94-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="49f94-104">ML.NET モデル ビルダーをインストールして .NET アプリケーションに機械学習を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49f94-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="49f94-105">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="49f94-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="49f94-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="49f94-106">Pre-requisites</span></span>

- <span data-ttu-id="49f94-107">Visual Studio 2017 15.9.12 以降 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="49f94-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="49f94-108">.NET Core 2.1 以降の SDK</span><span class="sxs-lookup"><span data-stu-id="49f94-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="49f94-109">制限事項</span><span class="sxs-lookup"><span data-stu-id="49f94-109">Limitations</span></span>

- <span data-ttu-id="49f94-110">ML.NET モデル ビルダー拡張機能は現在のところ、Windows 上の Visual Studio でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="49f94-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="49f94-111">トレーニング データセットの制限は 1 GB までの制限があります</span><span class="sxs-lookup"><span data-stu-id="49f94-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="49f94-112">SQL Server のトレーニング用の行は 10 万行までの制限があります。</span><span class="sxs-lookup"><span data-stu-id="49f94-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="49f94-113">Visual Studio 2017 用の Microsoft SQL Server Data Tools はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="49f94-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="49f94-114">インストール</span><span class="sxs-lookup"><span data-stu-id="49f94-114">Install</span></span>

<span data-ttu-id="49f94-115">ML.NET モデル ビルダーは、Visual Studio Marketplace または Visual Studio からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="49f94-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="49f94-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="49f94-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="49f94-117">[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) からダウンロード</span><span class="sxs-lookup"><span data-stu-id="49f94-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="49f94-118">指示に従って該当する Visual Studio バージョンにインストールします</span><span class="sxs-lookup"><span data-stu-id="49f94-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="49f94-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="49f94-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="49f94-120">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログを開く](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="49f94-122">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="49f94-123">検索バーで「*ML.NET モデル ビルダー*」を検索し、結果から「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してインストールする](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="49f94-125">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="49f94-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="49f94-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="49f94-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="49f94-127">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログを開く](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="49f94-129">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="49f94-130">検索バーに「*ML.NET モデル ビルダー*」と入力し、「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してインストールする](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="49f94-132">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="49f94-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="49f94-133">[アンインストール]</span><span class="sxs-lookup"><span data-stu-id="49f94-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="49f94-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="49f94-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="49f94-135">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 の [拡張機能の管理] ダイアログを開く](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="49f94-137">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="49f94-138">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してアンインストールする](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="49f94-140">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="49f94-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="49f94-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="49f94-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="49f94-142">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 の [拡張機能の管理] ダイアログを開く](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="49f94-144">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="49f94-145">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="49f94-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してアンインストールする](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="49f94-147">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="49f94-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="49f94-148">Upgrade</span><span class="sxs-lookup"><span data-stu-id="49f94-148">Upgrade</span></span>

<span data-ttu-id="49f94-149">アップグレード プロセスは、インストール プロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="49f94-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="49f94-150">Visual Studio Marketplace から最新バージョンをダウンロードするか、または Visual Studio で拡張機能マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="49f94-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
