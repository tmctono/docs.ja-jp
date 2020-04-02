---
title: Windows 8、Windows 8.1、または Windows 10 での .NET Framework 1.1 アプリの実行
description: Windows オペレーティング システムの多くのバージョンではサポートされなくなった、.NET Framework 1.1 を必要とするアプリに対応する方法について説明します。
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111791"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="d80a7-103">Windows 8、Windows 8.1、または Windows 10 での .NET Framework 1.1 アプリの実行</span><span class="sxs-lookup"><span data-stu-id="d80a7-103">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="d80a7-104">.NET Framework 1.1 は、Windows 8、Windows 8.1、Windows Server 2012、Windows Server 2012 R2、または Windows 10 の各オペレーティング システムではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d80a7-104">.NET Framework 1.1 is not supported on the Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2, or the Windows 10 operating systems.</span></span> <span data-ttu-id="d80a7-105">場合によっては、アプリを実行するために .NET Framework 1.1 が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d80a7-105">In some cases, .NET Framework 1.1 is required for an app to run.</span></span> <span data-ttu-id="d80a7-106">このような場合は、.NET Framework 3.5 SP1 以降のバージョンで実行するようにアプリケーションをアップグレードするように、独立系ソフトウェア ベンダー (ISV) 問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d80a7-106">In those cases, contact your independent software vendor (ISV) to have the app upgraded to run on .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="d80a7-107">詳細については、[.NET Framework 1.1 からの移行](../migration-guide/migrating-from-the-net-framework-1-1.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d80a7-107">For more information, see [Migrating from .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="d80a7-108">CD またはダウンロード センターから .NET Framework 1.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="d80a7-108">Install .NET Framework 1.1 from a CD or download center</span></span>

<span data-ttu-id="d80a7-109">CD またはダウンロード センターから、Windows 8、Windows 8.1、Windows Server 2012、Windows Server 2012 R2、または Windows 10 に .NET Framework 1.1 を手動でインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d80a7-109">It isn't possible to manually install .NET Framework 1.1 on Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2, or Windows 10 from a CD or download center.</span></span> <span data-ttu-id="d80a7-110">その機能はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d80a7-110">It's no longer supported.</span></span> <span data-ttu-id="d80a7-111">パッケージをインストールしようとすると、「このバージョンの .NET Framework は以前にインストールしたバージョンと互換性がないため、セットアップを続行できません。」というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d80a7-111">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="d80a7-112">この問題を解決するには、[.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22) をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d80a7-112">To solve this problem, install [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="d80a7-113">このバージョンには .NET Framework 2.0 (.NET Framework 1.1 の次のリリース) が含まれています。これは、Windows 8、Windows 8.1、および Windows 10 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d80a7-113">This version includes .NET Framework 2.0 (the release that follows .NET Framework 1.1), which is supported on Windows 8, Windows 8.1, and Windows 10.</span></span> <span data-ttu-id="d80a7-114">.NET Framework の新しいバージョンに自動的に更新されるかどうかを確認するために、常に最初にアプリケーションのインストールを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80a7-114">You should always try to install the app first to determine if it will automatically be updated to a later version of .NET Framework.</span></span> <span data-ttu-id="d80a7-115">更新されない場合は、アプリケーションの更新について ISV に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d80a7-115">If it doesn't, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="d80a7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d80a7-116">See also</span></span>

- [<span data-ttu-id="d80a7-117">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="d80a7-117">Migrating from the .NET Framework 1.1</span></span>](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="d80a7-118">Windows 10、Windows 8.1、および Windows 8 への .NET Framework 3.5 のインストール</span><span class="sxs-lookup"><span data-stu-id="d80a7-118">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>](dotnet-35-windows-10.md)
