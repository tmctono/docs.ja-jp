---
title: Docker ベースのアプリケーションの開発プロセス
description: Docker ベースのアプリケーションの開発のオプションに関する概要を確認します。 マルチ プラットフォームのサポート (Windows、macOS、Linux) のため、Windows 用 Visual Studio、Visual Studio for Mac、または Visual Studio Code のうち好みのものを使います。
ms.date: 01/30/2020
ms.openlocfilehash: 799aa6fc742a8fb763ec5a7ae3cf3f70f89bed6d
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502719"
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="1c1e8-104">Docker ベースのアプリケーションの開発プロセス</span><span class="sxs-lookup"><span data-stu-id="1c1e8-104">Development process for Docker-based applications</span></span>

<span data-ttu-id="1c1e8-105">*Visual Studio と Visual Studio Tools for Docker を使用した統合開発環境 (IDE)、または Docker CLI と Visual Studio Code を使用した CLI/エディターのお好きな方法でコンテナー化された .NET アプリケーションを開発します。*</span><span class="sxs-lookup"><span data-stu-id="1c1e8-105">*Develop containerized .NET applications the way you like, either Integrated Development Environment (IDE) focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="1c1e8-106">Docker アプリの開発環境</span><span class="sxs-lookup"><span data-stu-id="1c1e8-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="1c1e8-107">開発ツールの選択:IDE またはエディター</span><span class="sxs-lookup"><span data-stu-id="1c1e8-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="1c1e8-108">完全で強力な IDE または軽量でアジャイルなエディターのどちらを選んでも、Microsoft では Docker アプリケーションの開発に使用できるツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="1c1e8-109">**Visual Studio (Windows 版)。**</span><span class="sxs-lookup"><span data-stu-id="1c1e8-109">**Visual Studio (for Windows).**</span></span> <span data-ttu-id="1c1e8-110">Visual Studio での Docker ベースの .NET Core 3.1 アプリケーションの開発には、Visual Studio 2019 バージョン 16.4 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-110">Docker-based .NET Core 3.1 application development with Visual Studio requires Visual Studio 2019 version 16.4 or later.</span></span> <span data-ttu-id="1c1e8-111">Visual Studio 2019 には、既に Docker 用のツールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-111">Visual Studio 2019 comes with tools for Docker already built in.</span></span> <span data-ttu-id="1c1e8-112">Tools for Docker を使用して、ターゲットの Docker 環境で直接アプリケーションの開発、実行、および検証ができます。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-112">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="1c1e8-113">F5 キーを押すと、Docker ホスト内で直接アプリケーション (1 つのコンテナー、または複数のコンテナー) を実行してデバックできます。または、CTRL キーを押しながら F5 キーを押すと、コンテナーを再構築しなくても、アプリケーションを編集して更新できます。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-113">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="1c1e8-114">これは、Docker ベース アプリを開発する場合の最も強力な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-114">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="1c1e8-115">**Visual Studio for Mac。**</span><span class="sxs-lookup"><span data-stu-id="1c1e8-115">**Visual Studio for Mac.**</span></span> <span data-ttu-id="1c1e8-116">これは macOS で動作する、Xamarin Studio を進化させた IDE です。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-116">It's an IDE, evolution of Xamarin Studio, running in macOS.</span></span> <span data-ttu-id="1c1e8-117">.NET Core 3.1 で開発する場合、バージョン 8.4 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-117">For .NET Core 3.1 development, it requires version 8.4 or later.</span></span> <span data-ttu-id="1c1e8-118">これは、強力な IDE を使用したい macOS コンピューターで作業する開発者にとって好ましい選択肢です。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-118">This should be the preferred choice for developers working in macOS machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="1c1e8-119">**Visual Studio Code と Docker CLI**。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-119">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="1c1e8-120">すべての開発言語をサポートする軽量なクロスプラット フォーム エディターがよい場合は、Visual Studio Code と Docker CLI を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-120">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Visual Studio Code and the Docker CLI.</span></span> <span data-ttu-id="1c1e8-121">これは、macOS、Linux、Windows 向けのクロスプラット フォーム開発アプローチです。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-121">This is a cross-platform development approach for macOS, Linux, and Windows.</span></span> <span data-ttu-id="1c1e8-122">さらに、Visual Studio Code は、Dockerfiles の IntelliSense などの Docker の拡張機能や、エディターから Docker コマンドを実行するショートカット タスクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-122">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

<span data-ttu-id="1c1e8-123">[Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community) をインストールすることで、1 つの Docker CLI を使用して Windows と Linux の両方のアプリを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-123">By installing [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), you can use a single Docker CLI to build apps for both Windows and Linux.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1c1e8-124">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="1c1e8-124">Additional resources</span></span>

- <span data-ttu-id="1c1e8-125">**Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-125">**Visual Studio**.</span></span> <span data-ttu-id="1c1e8-126">公式サイト。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-126">Official site.</span></span> \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- <span data-ttu-id="1c1e8-127">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-127">**Visual Studio Code**.</span></span> <span data-ttu-id="1c1e8-128">公式サイト。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-128">Official site.</span></span> \
  <https://code.visualstudio.com/download>

- <span data-ttu-id="1c1e8-129">**Docker Desktop for Windows Community Edition (CE)**  </span><span class="sxs-lookup"><span data-stu-id="1c1e8-129">**Docker Desktop for Windows Community Edition (CE)** </span></span>\
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

- <span data-ttu-id="1c1e8-130">**Docker Desktop for Mac Community Edition (CE)**  </span><span class="sxs-lookup"><span data-stu-id="1c1e8-130">**Docker Desktop for Mac Community Edition (CE)** </span></span>\
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="1c1e8-131">.NET 言語および Docker コンテナーのフレームワーク</span><span class="sxs-lookup"><span data-stu-id="1c1e8-131">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="1c1e8-132">このガイドの前のセクションで触れたように、Docker コンテナー化された NET アプリケーションを開発する際に、.NET Framework、.NET Core、またはオープン ソースの Mono プロジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-132">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="1c1e8-133">Linux または Windows コンテナーをターゲットにする場合、使用している .NET Framework に応じて、C\#、F\#、または Visual Basic で開発できます。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-133">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="1c1e8-134">.NET 言語の詳細については、ブログ投稿「[The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/)」 (.NET 言語戦略) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c1e8-134">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1c1e8-135">[前へ](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[次へ](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1c1e8-135">[Previous](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
[Next](docker-app-development-workflow.md)</span></span>
