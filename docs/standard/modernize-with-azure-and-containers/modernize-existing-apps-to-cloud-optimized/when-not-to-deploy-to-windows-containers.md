---
title: Windows コンテナーを展開しない状況
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |Windows コンテナーをデプロイすべきでない場合
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 75db31a8f4599e9681c2c4156d93db5416d2ca96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200741"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="918f4-103">Windows コンテナーを展開しない状況</span><span class="sxs-lookup"><span data-stu-id="918f4-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="918f4-104">Windows コンテナーでは、一部の Windows テクノロジはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="918f4-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="918f4-105">その場合、引き続き Windows と IIS だけでは、通常、標準の Vm に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="918f4-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="918f4-106">2018 年 5 月の時点での Windows コンテナーではサポートされていない場合:</span><span class="sxs-lookup"><span data-stu-id="918f4-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="918f4-107">現在 Microsoft メッセージ キュー (MSMQ) は他の以前のリリースではなく Windows Server v1803 のリリースに基づく Windows コンテナーで使用可能なではのみです。</span><span class="sxs-lookup"><span data-stu-id="918f4-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="918f4-108">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="918f4-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="918f4-109">ディスカッション フォーラム</span><span class="sxs-lookup"><span data-stu-id="918f4-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="918f4-110">Microsoft 分散トランザクション コーディネーター (MSDTC) は、現在、Windows コンテナーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="918f4-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="918f4-111">GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="918f4-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="918f4-112">Microsoft Office は、現在のコンテナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="918f4-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="918f4-113">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="918f4-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="918f4-114">アプリの UI (ビジュアルなユーザー インターフェイスでクライアント アプリケーション) はサポートされているシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="918f4-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="918f4-115">Windows インフラストラクチャの役割 (DNS、DHCP、DC、NTP、印刷、ファイル サーバー、IAM など) はサポートされるシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="918f4-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="918f4-116">その他のサポートされていないシナリオと、コミュニティからの要求は、Windows コンテナーの UserVoice フォーラムを参照してください:<https://windowsserver.uservoice.com/forums/304624-containers>します。</span><span class="sxs-lookup"><span data-stu-id="918f4-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="918f4-117">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="918f4-117">Additional resources</span></span>

-   **<span data-ttu-id="918f4-118">仮想マシンと Azure でのコンテナー</span><span class="sxs-lookup"><span data-stu-id="918f4-118">Virtual machines and containers in Azure</span></span>**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
><span data-ttu-id="918f4-119">[前へ](deploy-existing-net-apps-as-windows-containers.md)
>[次へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="918f4-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>