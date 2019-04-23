---
title: Docker ベースのアプリケーションの開発プロセス
description: Docker ベースのアプリケーションの開発のオプションに関する大まかな概要を確認します。 マルチ プラットフォームのサポート (Windows、Mac、Linux) のため、Windows 用 Visual Studio、Visual Studio for Mac、または Visual Studio Code のうち好みのものを使います。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/27/2018
ms.openlocfilehash: de4ec036be4611ee56823ced3e0cddca5c32b900
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977706"
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="6032d-104">Docker ベースのアプリケーションの開発プロセス</span><span class="sxs-lookup"><span data-stu-id="6032d-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="6032d-105">*Visual Studio と Visual Studio Tools for Docker を使用して IDE に重点を置くか、Docker CLI と Visual Studio Code を使用して CLI/エディターに重点を置くか、好みの方法でコンテナー化された .NET アプリケーションを開発します。*</span><span class="sxs-lookup"><span data-stu-id="6032d-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="6032d-106">Docker アプリの開発環境</span><span class="sxs-lookup"><span data-stu-id="6032d-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="6032d-107">開発ツールの選択:IDE またはエディター</span><span class="sxs-lookup"><span data-stu-id="6032d-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="6032d-108">完全で強力な IDE または軽量でアジャイルなエディターのどちらを選んでも、Microsoft では Docker アプリケーションの開発に使用できるツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6032d-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="6032d-109">**Visual Studio (Windows 版)。**</span><span class="sxs-lookup"><span data-stu-id="6032d-109">**Visual Studio (for Windows).**</span></span> <span data-ttu-id="6032d-110">Visual Studio を使って Docker ベースのアプリケーションを開発する場合は、既に組み込まれている Docker 用ツールに付属する Visual Studio 2017 バージョン 15.7 以降を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6032d-110">When developing Docker-based applications with Visual Studio, it's recommended to use Visual Studio 2017 version 15.7 or later, that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="6032d-111">Tools for Docker を使用して、ターゲットの Docker 環境で直接アプリケーションの開発、実行、および検証ができます。</span><span class="sxs-lookup"><span data-stu-id="6032d-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="6032d-112">F5 キーを押すと、Docker ホスト内で直接アプリケーション (1 つのコンテナー、または複数のコンテナー) を実行してデバックできます。または、CTRL キーを押しながら F5 キーを押すと、コンテナーを再構築しなくても、アプリケーションを編集して更新できます。</span><span class="sxs-lookup"><span data-stu-id="6032d-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="6032d-113">これは、Docker ベース アプリを開発する場合の最も強力な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="6032d-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="6032d-114">**Visual Studio for Mac。**</span><span class="sxs-lookup"><span data-stu-id="6032d-114">**Visual Studio for Mac.**</span></span> <span data-ttu-id="6032d-115">これは macOS で動作する IDE であり、Xamarin Studio が進化したものです。2017 年中頃から Docker をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6032d-115">It's an IDE, evolution of Xamarin Studio, running in macOS and supports Docker since mid-2017.</span></span> <span data-ttu-id="6032d-116">これは、強力な IDE を使用したい Mac コンピューターで作業する開発者にとって好ましい選択肢です。</span><span class="sxs-lookup"><span data-stu-id="6032d-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="6032d-117">**Visual Studio Code と Docker CLI**。</span><span class="sxs-lookup"><span data-stu-id="6032d-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="6032d-118">任意の開発言語をサポートする軽量なクロスプラット フォーム エディターを選択すると、Microsoft Visual Studio Code (VS Code) と Docker CLI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6032d-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="6032d-119">これは、Mac、Linux、および Windows のクロスプラット フォーム開発アプローチです。</span><span class="sxs-lookup"><span data-stu-id="6032d-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span> <span data-ttu-id="6032d-120">さらに、Visual Studio Code は、Dockerfiles の IntelliSense などの Docker の拡張機能や、エディターから Docker コマンドを実行するショートカット タスクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6032d-120">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

<span data-ttu-id="6032d-121">[Docker Community Edition (CE)](https://www.docker.com/community-edition) ツールをインストールすることで、1 つの Docker CLI を使用して Windows と Linux の両方のアプリを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="6032d-121">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="6032d-122">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="6032d-122">Additional resources</span></span>

- <span data-ttu-id="6032d-123">**Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="6032d-123">**Visual Studio**.</span></span> <span data-ttu-id="6032d-124">公式サイト。</span><span class="sxs-lookup"><span data-stu-id="6032d-124">Official site.</span></span> \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- <span data-ttu-id="6032d-125">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="6032d-125">**Visual Studio Code**.</span></span> <span data-ttu-id="6032d-126">公式サイト。</span><span class="sxs-lookup"><span data-stu-id="6032d-126">Official site.</span></span> \
  <https://code.visualstudio.com/download>

- <span data-ttu-id="6032d-127">**Mac および Windows の Docker Community Edition (CE)** \\</span><span class="sxs-lookup"><span data-stu-id="6032d-127">**Docker Community Edition (CE) for Mac and Windows** \\</span></span>
  [https://www.docker.com/community-editions](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="6032d-128">.NET 言語および Docker コンテナーのフレームワーク</span><span class="sxs-lookup"><span data-stu-id="6032d-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="6032d-129">このガイドの前のセクションで触れたように、Docker コンテナー化された NET アプリケーションを開発する際に、.NET Framework、.NET Core、またはオープン ソースの Mono プロジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6032d-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="6032d-130">Linux または Windows コンテナーをターゲットにする場合、使用している .NET Framework に応じて、C\#、F\#、または Visual Basic で開発できます。</span><span class="sxs-lookup"><span data-stu-id="6032d-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="6032d-131">.NET 言語の詳細については、ブログ投稿「[The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/)」 (.NET 言語戦略) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6032d-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6032d-132">[前へ](../architect-microservice-container-applications/using-azure-service-fabric.md)
>[次へ](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6032d-132">[Previous](../architect-microservice-container-applications/using-azure-service-fabric.md)
[Next](docker-app-development-workflow.md)</span></span>
