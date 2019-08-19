---
title: Windows コンテナーを展開しない状況
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |Windows コンテナーに展開しない場合
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577955"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="991bf-103">Windows コンテナーを展開しない状況</span><span class="sxs-lookup"><span data-stu-id="991bf-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="991bf-104">一部の Windows テクノロジは、Windows コンテナーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="991bf-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="991bf-105">そのような場合でも、通常は Windows と IIS だけを使用して標準 Vm に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="991bf-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="991bf-106">Windows コンテナーでサポートされていないケース (2018 年5月):</span><span class="sxs-lookup"><span data-stu-id="991bf-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="991bf-107">Microsoft Message Queuing (MSMQ) は、現在、Windows Server v1803 リリースに基づく Windows コンテナーでのみ使用できますが、それ以外の以前のリリースでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="991bf-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="991bf-108">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="991bf-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="991bf-109">ディスカッションフォーラム</span><span class="sxs-lookup"><span data-stu-id="991bf-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="991bf-110">Microsoft 分散トランザクションコーディネーター (MSDTC) は、現在、Windows コンテナーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="991bf-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="991bf-111">GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="991bf-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="991bf-112">Microsoft Office は現在、コンテナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="991bf-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="991bf-113">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="991bf-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="991bf-114">UI アプリ (ビジュアルユーザーインターフェイスを使用したクライアントアプリ) は、サポートされていないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="991bf-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="991bf-115">Windows インフラストラクチャの役割 (DNS、DHCP、DC、NTP、印刷、ファイルサーバー、IAM など) は、サポートされていないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="991bf-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="991bf-116">コミュニティからのサポートされていないその他のシナリオと要求については、 <https://windowsserver.uservoice.com/forums/304624-containers>「Windows コンテナーの UserVoice フォーラム:」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991bf-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="991bf-117">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="991bf-117">Additional resources</span></span>

- <span data-ttu-id="991bf-118">**Azure の仮想マシンとコンテナー**</span><span class="sxs-lookup"><span data-stu-id="991bf-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="991bf-119">[前へ](deploy-existing-net-apps-as-windows-containers.md)
> [次へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="991bf-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
