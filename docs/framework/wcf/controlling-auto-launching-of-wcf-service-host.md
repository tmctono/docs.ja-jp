---
title: WCF サービス ホストの自動起動の制御
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 806d85df2a7fff63704db755400b81cc2dc5c37b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652085"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="2d7c0-102">WCF サービス ホストの自動起動の制御</span><span class="sxs-lookup"><span data-stu-id="2d7c0-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="2d7c0-103">複数のプロジェクトを含む同じ Visual Studio ソリューション内の別のプロジェクトをデバッグする場合は、WCF サービス ライブラリ プロジェクトでは、Windows Communication Foundation (WCF) サービス ホスト (WcfSvcHost.exe) の自動起動機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="2d7c0-104">これを行うで WCF サービス プロジェクトを右クリックし**ソリューション エクスプ ローラー**、選択**プロパティ**、 をクリック**WCF オプション**タブ。**開始 WCF サービス ホスト、同じソリューション内の別のプロジェクトをデバッグするときに** チェック ボックスが既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="2d7c0-105">同じソリューションで別のプロジェクトのデバッグ時に、この特定のプロジェクトの WCF サービス ホストが起動しないように、ボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="2d7c0-106">この動作は、F5 キーによるデバッグや、このプロジェクトへのサービス参照の追加の機能には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="2d7c0-107">このオプションは、次のプロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="2d7c0-108">WCF サービス ライブラリ プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d7c0-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="2d7c0-109">シーケンシャル ワークフロー サービス ライブラリ プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2d7c0-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="2d7c0-110">ステート マシン ワークフロー サービス ライブラリ プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2d7c0-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="2d7c0-111">配信サービス ライブラリ プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2d7c0-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7c0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d7c0-112">See also</span></span>

- [<span data-ttu-id="2d7c0-113">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2d7c0-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
