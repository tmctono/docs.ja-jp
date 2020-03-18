---
title: モデル ビルダーのインストール方法
description: ML.NET モデル ビルダー ツールのインストール方法について説明します
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: b944d7f6044553251132824e7e4213119e34500e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848653"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="80509-103">ML.NET モデル ビルダーのインストール方法</span><span class="sxs-lookup"><span data-stu-id="80509-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="80509-104">ML.NET モデル ビルダーをインストールして .NET アプリケーションに機械学習を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80509-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="80509-105">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="80509-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80509-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="80509-106">Prerequisites</span></span>

- <span data-ttu-id="80509-107">Visual Studio 2017 バージョン 15.9.12 以降 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="80509-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="80509-108">.NET Core 2.1 SDK 以降。</span><span class="sxs-lookup"><span data-stu-id="80509-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="80509-109">.NET Core 3.0 SDK は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80509-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="80509-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="80509-110">Limitations</span></span>

- <span data-ttu-id="80509-111">ML.NET モデル ビルダー拡張機能は現在のところ、Windows 上の Visual Studio でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="80509-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="80509-112">トレーニング データセットの制限は 1 GB までの制限があります</span><span class="sxs-lookup"><span data-stu-id="80509-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="80509-113">SQL Server のトレーニング用の行は 10 万行までの制限があります。</span><span class="sxs-lookup"><span data-stu-id="80509-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="80509-114">Visual Studio 2017 用の Microsoft SQL Server Data Tools はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="80509-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="80509-115">インストール</span><span class="sxs-lookup"><span data-stu-id="80509-115">Install</span></span>

<span data-ttu-id="80509-116">ML.NET モデル ビルダーは、Visual Studio Marketplace または Visual Studio からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="80509-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="80509-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="80509-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="80509-118">[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) からダウンロード</span><span class="sxs-lookup"><span data-stu-id="80509-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="80509-119">指示に従って該当する Visual Studio バージョンにインストールします</span><span class="sxs-lookup"><span data-stu-id="80509-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="80509-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="80509-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="80509-121">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="80509-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログを開く](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="80509-123">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="80509-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="80509-124">検索バーで「*ML.NET モデル ビルダー*」を検索し、結果から「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してインストールする](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="80509-126">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="80509-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="80509-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="80509-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="80509-128">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="80509-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログを開く](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="80509-130">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="80509-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="80509-131">検索バーに「*ML.NET モデル ビルダー*」と入力し、「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してインストールする](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="80509-133">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="80509-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="80509-134">[アンインストール]</span><span class="sxs-lookup"><span data-stu-id="80509-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="80509-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="80509-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="80509-136">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="80509-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 の [拡張機能の管理] ダイアログを開く](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="80509-138">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="80509-139">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してアンインストールする](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="80509-141">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="80509-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="80509-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="80509-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="80509-143">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="80509-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 の [拡張機能の管理] ダイアログを開く](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="80509-145">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="80509-146">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="80509-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 の拡張機能マネージャー ダイアログでモデル ビルダー拡張機能を検索してアンインストールする](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="80509-148">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="80509-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="80509-149">アップグレード</span><span class="sxs-lookup"><span data-stu-id="80509-149">Upgrade</span></span>

<span data-ttu-id="80509-150">アップグレード プロセスは、インストール プロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="80509-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="80509-151">Visual Studio Marketplace から最新バージョンをダウンロードするか、または Visual Studio で拡張機能マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="80509-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
