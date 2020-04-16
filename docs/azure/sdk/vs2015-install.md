---
title: Azure Tools for Visual Studio 2015
description: ツールを入手し、Visual Studio 2015 からの Azure .NET ライブラリの使用を始めてください。
ms.date: 10/19/2017
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: a29709d56f2debe04d49ee4eafdc27acd4ca480f
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433152"
---
# <a name="azure-tools-for-visual-studio-2015"></a><span data-ttu-id="900ec-103">Azure Tools for Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="900ec-103">Azure tools for Visual Studio 2015</span></span>

<span data-ttu-id="900ec-104">**Azure SDK for Visual Studio 2015** および **Service Fabric SDK and Tools for Visual Studio 2015** をインストールする最も速くて簡単方法は、[Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx) を使うことです。</span><span class="sxs-lookup"><span data-stu-id="900ec-104">The quickest and easiest way to install the **Azure SDK for Visual Studio 2015** and **Service Fabric SDK and Tools for Visual Studio 2015** is using the [Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx).</span></span> <span data-ttu-id="900ec-105">Microsoft Web Platform Installer は無料ツールであり、Azure Tools for Visual Studio 2015 などの Microsoft Web Platform の一部のコンポーネントのダウンロード、インストール、更新を効率化します。</span><span class="sxs-lookup"><span data-stu-id="900ec-105">The Microsoft Web Platform Installer is a free tool that streamlines downloading, installing, and updating some of the components of the Microsoft Web Platform, including Azure tools for Visual Studio 2015.</span></span> <span data-ttu-id="900ec-106">これらの SDK は、[Azure のダウンロード ページ](https://azure.microsoft.com/downloads/)から個別のコンポーネントとしてダウンロードしてインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="900ec-106">These SDKs can also be downloaded and installed as individual components from the [Azure Downloads page](https://azure.microsoft.com/downloads/).</span></span>

## <a name="using-the-web-platform-installer"></a><span data-ttu-id="900ec-107">Web Platform Installer の使用</span><span class="sxs-lookup"><span data-stu-id="900ec-107">Using the Web Platform Installer</span></span>

1. <span data-ttu-id="900ec-108">この [Web Platform Installer ブートストラッパー](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=VWDOrVs2015AzurePack;MicrosoftAzure-ServiceFabric-VS2015)をダウンロードして実行します。</span><span class="sxs-lookup"><span data-stu-id="900ec-108">Download and run this [Web Platform Installer bootstrapper](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=VWDOrVs2015AzurePack;MicrosoftAzure-ServiceFabric-VS2015).</span></span>

2. <span data-ttu-id="900ec-109">ブートストラッパーは、(必要に応じて) Web Platform Installer をインストールし、**Azure SDK for Visual Studio 2015** および **Service Fabric SDK and Tools for Visual Studio 2015** 項目の最新バージョンを、"*インストールする項目*" のリストに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="900ec-109">The bootstrapper will install Web Platform Installer (if needed) and automatically put the latest versions of the  **Azure SDK for Visual Studio 2015** and **Service Fabric SDK and Tools for Visual Studio 2015** items in your *Items to be installed* list.</span></span> <span data-ttu-id="900ec-110">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="900ec-110">Click **Install**.</span></span>

    ![Web Platform Installer](../media/sdk/vs2015-install/webpi.png)

3. <span data-ttu-id="900ec-112">次の画面で、**[同意する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="900ec-112">On the next screen, click **I Accept**.</span></span> <span data-ttu-id="900ec-113">Web PI が、選択したコンポーネントのダウンロードとインストールを始めます。</span><span class="sxs-lookup"><span data-stu-id="900ec-113">Web PI will begin downloading and installing the components you selected.</span></span>

4. <span data-ttu-id="900ec-114">インストールが完了すると、確認画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="900ec-114">After the installation is finished, it will display a confirmation screen.</span></span> <span data-ttu-id="900ec-115">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="900ec-115">Click **Finish**.</span></span> <span data-ttu-id="900ec-116">Web Platform Installer を閉じてかまいません。</span><span class="sxs-lookup"><span data-stu-id="900ec-116">You can now close Web Platform Installer.</span></span>

## <a name="verifying-the-installation"></a><span data-ttu-id="900ec-117">インストールの確認</span><span class="sxs-lookup"><span data-stu-id="900ec-117">Verifying the installation</span></span>

1. <span data-ttu-id="900ec-118">Visual Studio 2015 で、**[ツール]** メニューの **[拡張機能と更新プログラム...]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="900ec-118">In Visual Studio 2015, click the **Tools** menu, and then click **Extensions and Updates...**.</span></span>

2. <span data-ttu-id="900ec-119">表示される一覧には、**Microsoft Azure App Service Tools**、**Microsoft Azure Storage 接続済みサービス**、**Service Fabric Tools** など、複数の Azure ツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="900ec-119">The displayed list will contain several Azure tools, such as **Microsoft Azure App Service Tools**, **Microsoft Azure Storage Connected Service**, and **Service Fabric Tools**.</span></span>

    ![拡張機能と更新プログラム](../media/sdk/vs2015-install/ext-tools.png)
