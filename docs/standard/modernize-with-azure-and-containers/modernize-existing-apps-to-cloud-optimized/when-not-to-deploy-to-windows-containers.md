---
title: Windows コンテナーを展開しない状況
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |Windows コンテナーをデプロイすべきでない場合
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: e06793065d1fd55bbef855576174b07dc9ace4c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751390"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="e1d99-103">Windows コンテナーを展開しない状況</span><span class="sxs-lookup"><span data-stu-id="e1d99-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="e1d99-104">Windows コンテナーでは、一部の Windows テクノロジはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1d99-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="e1d99-105">その場合、引き続き Windows と IIS だけでは、通常、標準の Vm に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d99-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="e1d99-106">2018 年 5 月の時点での Windows コンテナーではサポートされていない場合:</span><span class="sxs-lookup"><span data-stu-id="e1d99-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="e1d99-107">現在 Microsoft メッセージ キュー (MSMQ) は他の以前のリリースではなく Windows Server v1803 のリリースに基づく Windows コンテナーで使用可能なではのみです。</span><span class="sxs-lookup"><span data-stu-id="e1d99-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="e1d99-108">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="e1d99-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="e1d99-109">ディスカッション フォーラム</span><span class="sxs-lookup"><span data-stu-id="e1d99-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="e1d99-110">Microsoft 分散トランザクション コーディネーター (MSDTC) は、現在、Windows コンテナーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e1d99-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="e1d99-111">GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="e1d99-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="e1d99-112">Microsoft Office は、現在のコンテナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e1d99-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="e1d99-113">UserVoice 要求フォーラム</span><span class="sxs-lookup"><span data-stu-id="e1d99-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="e1d99-114">アプリの UI (ビジュアルなユーザー インターフェイスでクライアント アプリケーション) はサポートされているシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="e1d99-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="e1d99-115">Windows インフラストラクチャの役割 (DNS、DHCP、DC、NTP、印刷、ファイル サーバー、IAM など) はサポートされるシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="e1d99-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="e1d99-116">その他のサポートされていないシナリオと、コミュニティからの要求は、Windows コンテナーの UserVoice フォーラムを参照してください:<https://windowsserver.uservoice.com/forums/304624-containers>します。</span><span class="sxs-lookup"><span data-stu-id="e1d99-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e1d99-117">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="e1d99-117">Additional resources</span></span>

- <span data-ttu-id="e1d99-118">**仮想マシンと Azure でのコンテナー**</span><span class="sxs-lookup"><span data-stu-id="e1d99-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="e1d99-119">[前へ](deploy-existing-net-apps-as-windows-containers.md)
> [次へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="e1d99-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
