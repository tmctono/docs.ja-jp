---
title: .NET Framework ドキュメント
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5a86b3abf821a37944a0e478d0bc8f1bea31ccb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699052"
---
# <a name="net-framework-guide"></a><span data-ttu-id="f22b3-102">.NET Framework ガイド</span><span class="sxs-lookup"><span data-stu-id="f22b3-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="f22b3-103">この .NET Framework コンテンツ セットには .NET Framework バージョン 4.5 から 4.8 に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f22b3-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="f22b3-104">.NET Framework をダウンロードするには、「[.NET Framework のインストール](./install/guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="f22b3-105">.NET Framework での新機能と変更点の一覧については、「[.NET Framework の新機能](./whats-new/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="f22b3-106">サポートされているプラットフォームについては、「[.NET Framework のシステム要件](./get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="f22b3-107">以前のバージョンの .NET Framework に関するドキュメントについては、「[.NET Framework の以前のバージョンのドキュメント](https://docs.microsoft.com/previous-versions/dotnet/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="f22b3-108">.NET Framework は、Web、Windows、Windows Phone、Windows Server、および Microsoft Azure 用のアプリを作成するための開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="f22b3-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="f22b3-109">共通言語ランタイム (CLR) と .NET Framework クラス ライブラリで構成され、さまざまな機能を含み、さまざまな業界標準をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f22b3-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="f22b3-110">.NET Framework は、メモリ管理、型とメモリの安全性、セキュリティ、ネットワーク、およびアプリケーションの展開など、多くのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="f22b3-111">使いやすいデータ構造と下位レベルの Windows オペレーティング システムを抽象化する API を提供します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="f22b3-112">.NET Framework では、C#、F#、Visual Basic を含む、さまざまなプログラミング言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f22b3-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="f22b3-113">ユーザーと開発者のための .NET Framework の概要については、「[.NET Framework の概要](./get-started/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="f22b3-114">.NET Framework のアーキテクチャおよび主要機能の概要については、[「.NET Framework overview の概要」](./get-started/overview.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="f22b3-115">.NET Framework は、Docker との併用および [Windows コンテナー](/virtualization/windowscontainers/about/)との併用が可能です。</span><span class="sxs-lookup"><span data-stu-id="f22b3-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="f22b3-116">インストール</span><span class="sxs-lookup"><span data-stu-id="f22b3-116">Installation</span></span>

<span data-ttu-id="f22b3-117">.NET Framework は、Windows に付属しているので .NET Framework アプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f22b3-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="f22b3-118">Windows に付属しているバージョンよりも、新しいバージョンの .NET Framework が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f22b3-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="f22b3-119">詳細については、「[Windows への .NET Framework のインストール](./install/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="f22b3-120">.NET Framework をインストールするときにエラーが発生する場合に .NET Framework のインストールを修復する方法については、「[.NET Framework を修復する](./install/repair.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="f22b3-121">.NET Framework のダウンロードの詳細については、「[開発者向けの .NET Framework のインストール](./install/guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22b3-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f22b3-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f22b3-122">In this section</span></span>

* [<span data-ttu-id="f22b3-123">新機能</span><span class="sxs-lookup"><span data-stu-id="f22b3-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="f22b3-124">最新バージョンの .NET Framework の主要な新機能と変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="f22b3-125">現在使用されていない型とメンバーのリストを示し、.NET Framework の以前のバージョンからアプリケーションを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="f22b3-126">開始するには</span><span class="sxs-lookup"><span data-stu-id="f22b3-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="f22b3-127">.NET Framework の包括的な概要と、追加リソースへのリンクを説明します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="f22b3-128">インストール ガイド</span><span class="sxs-lookup"><span data-stu-id="f22b3-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="f22b3-129">.NET Framework のインストールとトラブルシューティングに関するリソースとガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="f22b3-130">移行ガイド</span><span class="sxs-lookup"><span data-stu-id="f22b3-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="f22b3-131">アプリケーションを新しいバージョンの .NET Framework に移行する場合に検討する必要のあるリソースと変更の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="f22b3-132">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="f22b3-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="f22b3-133">アプリケーションの作成、構成、デバッグ、セキュリティ、配置、および動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理に関する情報を含む、アプリケーション開発用の主要な技術領域とタスクのすべてについての手引書です。</span><span class="sxs-lookup"><span data-stu-id="f22b3-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="f22b3-134">ツール</span><span class="sxs-lookup"><span data-stu-id="f22b3-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="f22b3-135">.NET Framework テクノロジを使ってアプリケーションを開発、構成、配置するのに役立つツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="f22b3-136">追加のクラス ライブラリおよび API</span><span class="sxs-lookup"><span data-stu-id="f22b3-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="f22b3-137">Microsoft のツールで使用されるプライベート .NET Framework API のドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="f22b3-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="f22b3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="f22b3-138">See also</span></span>

- [<span data-ttu-id="f22b3-139">.NET Framework クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f22b3-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
