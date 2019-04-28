---
title: WCF Discovery
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768694"
---
# <a name="wcf-discovery"></a><span data-ttu-id="28785-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="28785-102">WCF Discovery</span></span>
<span data-ttu-id="28785-103">Windows Communication Foundation (WCF) は、Ws-discovery プロトコルを使用して、相互運用可能な方法で実行時に検出するサービスを有効にするサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="28785-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="28785-104">WCF サービスは、マルチキャスト メッセージを使用してネットワークまたは探索プロキシ サーバーには、その可用性を知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="28785-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="28785-105">クライアント アプリケーションは、ネットワークまたは探索プロキシ サーバーを検索して、一連の基準を満たすサービスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="28785-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="28785-106">このセクションのトピックでは、この機能の概要を示し、そのプログラミング モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28785-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28785-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="28785-107">In This Section</span></span>  
 [<span data-ttu-id="28785-108">WCF Discovery の概要</span><span class="sxs-lookup"><span data-stu-id="28785-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="28785-109">WCF で提供する Ws-discovery サポートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="28785-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="28785-110">WCF Discovery オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="28785-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="28785-111">オブジェクト モデルのクラスと WS-Discovery サポートの拡張性について説明します。</span><span class="sxs-lookup"><span data-stu-id="28785-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="28785-112">方法: 探索可能性を WCF サービスとクライアントにプログラムで追加します。</span><span class="sxs-lookup"><span data-stu-id="28785-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="28785-113">Windows Communication Foundation (WCF) サービスを探索可能にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28785-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="28785-114">探索プロキシの実装</span><span class="sxs-lookup"><span data-stu-id="28785-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="28785-115">探索プロキシを実装するのに必要な手順、探索プロキシで登録される探索可能なサービス、および探索プロキシを使用して探索可能なサービスを検索するクライアントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28785-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="28785-116">探索機能のバージョン指定</span><span class="sxs-lookup"><span data-stu-id="28785-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="28785-117">いくつかの新しい探索機能のプロトタイプ実装の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="28785-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="28785-118">使用する探索バージョンを選択する方法の概要も示します。</span><span class="sxs-lookup"><span data-stu-id="28785-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="28785-119">構成ファイルにおける探索の構成</span><span class="sxs-lookup"><span data-stu-id="28785-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="28785-120">構成ファイルで探索を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28785-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="28785-121">探索クライアント チャネルの使用</span><span class="sxs-lookup"><span data-stu-id="28785-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="28785-122">WCF クライアント アプリケーションを作成するときに、探索クライアント チャネルを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28785-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
