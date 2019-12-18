---
title: Windows 8、Windows 8.1、または Windows 10 での .NET Framework 1.1 アプリの実行
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1364eebf4d94a117a3ee7f0912b6ff4090e93853
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960036"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="24b75-102">Windows 8、Windows 8.1、または Windows 10 での .NET Framework 1.1 アプリの実行</span><span class="sxs-lookup"><span data-stu-id="24b75-102">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="24b75-103">.NET Framework 1.1 は、Windows 8、Windows 8.1、Windows Server 2012、[!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)]、または Windows 10 の各オペレーティング システムではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="24b75-103">The .NET Framework 1.1 is not supported on the Windows 8, Windows 8.1, Windows Server 2012, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or the Windows 10 operating systems.</span></span> <span data-ttu-id="24b75-104">場合によっては、アプリケーションの実行に .NET Framework 1.1 が特別に指定されています。</span><span class="sxs-lookup"><span data-stu-id="24b75-104">In some cases, the .NET Framework 1.1 is specifically identified as required for an app to run.</span></span> <span data-ttu-id="24b75-105">このような場合は、.NET Framework 3.5 SP1 以降のバージョンで実行するためにアプリケーションをアップグレードするように、独立ソフトウェア ベンダー (ISV) に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24b75-105">In those cases, you should contact your independent software vendor (ISV) to have the app upgraded to run on the .NET Framework 3.5 SP1 or later version.</span></span> <span data-ttu-id="24b75-106">詳細については、「[.NET Framework 1.1 からの移行](../migration-guide/migrating-from-the-net-framework-1-1.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24b75-106">For additional information, see [Migrating from the .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="24b75-107">CD またはダウンロード センターからの .NET Framework 1.1 のインストール</span><span class="sxs-lookup"><span data-stu-id="24b75-107">Install the .NET Framework 1.1 from a CD or Download Center</span></span>

<span data-ttu-id="24b75-108">Windows 8、Windows 8.1、Windows Server 2012、[!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)]、または Windows 10 に .NET Framework 1.1 を手動でインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="24b75-108">It isn't possible to manually install the .NET Framework 1.1 on Windows 8, Windows 8.1, Windows Server 2012, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or Windows 10.</span></span> <span data-ttu-id="24b75-109">サポート対象から除外されました。</span><span class="sxs-lookup"><span data-stu-id="24b75-109">It is no longer supported.</span></span> <span data-ttu-id="24b75-110">パッケージをインストールしようとすると、「このバージョンの .NET Framework は以前にインストールしたバージョンと互換性がないため、セットアップを続行できません。」というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b75-110">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="24b75-111">この問題を解決するには、[.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="24b75-111">To solve this problem, install the [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="24b75-112">このバージョンには .NET Framework 2.0 (.NET Framework 1.1 の次のリリース) が含まれています。これは、Windows 8、Windows 8.1、および Windows 10 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="24b75-112">This version includes the .NET Framework 2.0 (the release that follows the .NET Framework 1.1), which is supported on Windows 8, Windows 8.1, and Windows 10.</span></span> <span data-ttu-id="24b75-113">.NET Framework の新しいバージョンに自動的に更新されるかどうかを確認するために、常に最初にアプリケーションのインストールを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="24b75-113">You should always try to install the app first to determine if it will automatically be updated to a later version of the .NET Framework.</span></span> <span data-ttu-id="24b75-114">更新されない場合は、アプリケーションの更新について ISV に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="24b75-114">If it does not, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b75-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b75-115">See also</span></span>

- [<span data-ttu-id="24b75-116">.NET Framework 1.1 からの移行</span><span class="sxs-lookup"><span data-stu-id="24b75-116">Migrating from the .NET Framework 1.1</span></span>](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="24b75-117">Windows 10、Windows 8.1、および Windows 8 への .NET Framework 3.5 のインストール</span><span class="sxs-lookup"><span data-stu-id="24b75-117">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>](dotnet-35-windows-10.md)
