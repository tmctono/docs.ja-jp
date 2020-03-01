---
title: .NET Core SDK の概要
description: .NET Core プロジェクトの作成に使用するライブラリとツールのセットである .NET Core SDK について説明します。
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: c2723e0e28c889f91f79ea3c0b26aa38f69fb41c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157467"
---
# <a name="net-core-sdk-overview"></a><span data-ttu-id="47cf1-103">.NET Core SDK の概要</span><span class="sxs-lookup"><span data-stu-id="47cf1-103">.NET Core SDK overview</span></span>

<span data-ttu-id="47cf1-104">.NET Core SDK は一連のライブラリとツールであり、開発者はこれを利用して .NET Core のアプリケーションやライブラリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47cf1-104">The .NET Core SDK is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="47cf1-105">それには、アプリケーションのビルドと実行に使用される次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="47cf1-105">It contains the following components that are used to build and run applications:</span></span>

- <span data-ttu-id="47cf1-106">.NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="47cf1-106">The .NET Core CLI.</span></span>
- <span data-ttu-id="47cf1-107">.NET Core ライブラリとランタイム。</span><span class="sxs-lookup"><span data-stu-id="47cf1-107">.NET Core libraries and runtime.</span></span>
- <span data-ttu-id="47cf1-108">`dotnet` [ドライバー](tools/index.md#driver)。</span><span class="sxs-lookup"><span data-stu-id="47cf1-108">The `dotnet` [driver](tools/index.md#driver).</span></span>

## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="47cf1-109">.NET Core SDK を入手する</span><span class="sxs-lookup"><span data-stu-id="47cf1-109">Acquiring the .NET Core SDK</span></span>

<span data-ttu-id="47cf1-110">他のツールと同様に、最初にコンピューターにツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47cf1-110">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="47cf1-111">シナリオに応じて、次のいずれかの方法で SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="47cf1-111">Depending on your scenario, you can install the SDK using one of the following methods:</span></span>

- <span data-ttu-id="47cf1-112">ネイティブ インストーラーを使う。</span><span class="sxs-lookup"><span data-stu-id="47cf1-112">Use the native installers.</span></span>
- <span data-ttu-id="47cf1-113">インストール シェル スクリプトを使う。</span><span class="sxs-lookup"><span data-stu-id="47cf1-113">Use the installation shell script.</span></span>

<span data-ttu-id="47cf1-114">開発者のコンピューターでは、ネイティブ インストーラーが利用されることが多いです。</span><span class="sxs-lookup"><span data-stu-id="47cf1-114">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="47cf1-115">SDK はサポートされるプラットフォームのネイティブ インストール メカニズムにより配信されます。たとえば、Ubuntu の場合は DEB パッケージ、Windows の場合は MSI バンドルです。</span><span class="sxs-lookup"><span data-stu-id="47cf1-115">The SDK is distributed using each supported platform's native install mechanism, such as DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="47cf1-116">これらのインストーラーでは、インストール直後に、ユーザーが SDK を使うために必要な環境がインストールされて設定されます。</span><span class="sxs-lookup"><span data-stu-id="47cf1-116">These installers install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="47cf1-117">ただし、コンピューター上で管理者特権も必要になります。</span><span class="sxs-lookup"><span data-stu-id="47cf1-117">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="47cf1-118">インストールする SDK は、[.NET ダウンロード](https://dotnet.microsoft.com/download) ページで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="47cf1-118">You can find the SDK to install on the [.NET downloads](https://dotnet.microsoft.com/download) page.</span></span>

<span data-ttu-id="47cf1-119">一方、インストール スクリプトでは、管理者特権は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="47cf1-119">Install scripts, on the other hand, don't require administrative privileges.</span></span> <span data-ttu-id="47cf1-120">ただし、いかなる前提条件もコンピューターにインストールされません。前提条件はすべてユーザーが手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47cf1-120">However, they also don't install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="47cf1-121">スクリプトは、通常、管理者特権なしでツールをインストールするとき、ビルド サーバーを設定するために利用されます (上の前提条件警告に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="47cf1-121">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="47cf1-122">詳しくは、[インストール スクリプト リファレンス](tools/dotnet-install-script.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47cf1-122">You can find more information in the [install script reference](tools/dotnet-install-script.md) article.</span></span> <span data-ttu-id="47cf1-123">お使いの CI ビルド サーバーで SDK を設定する方法について関心がある場合は、「[継続的インテグレーション (CI) で .NET Core SDK とツールを使用する](tools/using-ci-with-cli.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47cf1-123">If you're interested in how to set up the SDK on your CI build server, see the [Using .NET Core SDK and tools in Continuous Integration (CI)](tools/using-ci-with-cli.md) article.</span></span>

<span data-ttu-id="47cf1-124">既定では、SDK は "side-by-side" (SxS) 方式でインストールされます。つまり、複数のバージョンを 1 台のコンピューター上にいつでも共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="47cf1-124">By default, the SDK installs in a "side-by-side" (SxS) manner, which means multiple versions can coexist at any given time on a single machine.</span></span> <span data-ttu-id="47cf1-125">CLI コマンドを実行したときにバージョンが選択される方法について詳しくは、「[使用する .NET Core のバージョンを選択する](versions/selection.md)」記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47cf1-125">How the version gets picked when you're running CLI commands is explained in more detail in the [Select the .NET Core version to use](versions/selection.md) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="47cf1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="47cf1-126">See also</span></span>

- [<span data-ttu-id="47cf1-127">.NET Core CLI の概要</span><span class="sxs-lookup"><span data-stu-id="47cf1-127">.NET Core CLI overview</span></span>](tools/index.md)
- [<span data-ttu-id="47cf1-128">.NET Core のバージョン管理の概要</span><span class="sxs-lookup"><span data-stu-id="47cf1-128">.NET Core versioning overview</span></span>](versions/index.md)
- [<span data-ttu-id="47cf1-129">.NET Core ランタイムと SDK を削除する方法</span><span class="sxs-lookup"><span data-stu-id="47cf1-129">How to remove the .NET Core runtime and SDK</span></span>](versions/remove-runtime-sdk-versions.md)
- [<span data-ttu-id="47cf1-130">使用する .NET Core のバージョンを選択する</span><span class="sxs-lookup"><span data-stu-id="47cf1-130">Select the .NET Core version to use</span></span>](versions/selection.md)
