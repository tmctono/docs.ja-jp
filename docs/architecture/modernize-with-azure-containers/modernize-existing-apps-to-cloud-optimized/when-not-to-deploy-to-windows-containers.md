---
title: Windows コンテナーを展開しない状況
description: Azure Cloud と Windows コンテナーで既存の .NET アプリケーションを最新化する | Windows コンテナーをデプロイしない状況
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577955"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="a6743-103">Windows コンテナーを展開しない状況</span><span class="sxs-lookup"><span data-stu-id="a6743-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="a6743-104">一部の Windows テクノロジは、Windows コンテナーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6743-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="a6743-105">そのような場合でも、通常は Windows と IIS だけを使用して標準 VM に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6743-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="a6743-106">Windows コンテナーでサポートされていないケース (2018 年 5 月):</span><span class="sxs-lookup"><span data-stu-id="a6743-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="a6743-107">Microsoft メッセージ キュー (MSMQ) は現在のところ、Windows Server v1803 リリースをベースとする Windows コンテナーでのみ利用できます。それ以前のリリースでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="a6743-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="a6743-108">UserVoice リクエスト フォーラム</span><span class="sxs-lookup"><span data-stu-id="a6743-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="a6743-109">ディスカッション フォーラム</span><span class="sxs-lookup"><span data-stu-id="a6743-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="a6743-110">Microsoft 分散トランザクション コーディネーター (MSDTC) は現在のところ、Windows コンテナーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6743-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="a6743-111">GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="a6743-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="a6743-112">Microsoft Office では現在、コンテナーがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6743-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="a6743-113">UserVoice リクエスト フォーラム</span><span class="sxs-lookup"><span data-stu-id="a6743-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="a6743-114">UI アプリ (ビジュアル ユーザー インターフェイスのあるクライアント アプリ) は、サポートされていないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="a6743-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="a6743-115">Windows インフラストラクチャの役割 (DNS、DHCP、DC、NTP、PRINT、ファイル サーバー、IAM など) は、サポートされていないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="a6743-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="a6743-116">他の未サポート シナリオやコミュニティからのリクエストについては、Windows コンテナーの UserVoice フォーラム <https://windowsserver.uservoice.com/forums/304624-containers> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6743-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a6743-117">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="a6743-117">Additional resources</span></span>

- <span data-ttu-id="a6743-118">**Azure 内の仮想マシンとコンテナー**</span><span class="sxs-lookup"><span data-stu-id="a6743-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="a6743-119">[前へ](deploy-existing-net-apps-as-windows-containers.md)
> [次へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="a6743-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
