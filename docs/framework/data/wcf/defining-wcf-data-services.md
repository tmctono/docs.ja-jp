---
title: WCF Data Services の定義
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: 26cfee95f7cd3b956ff263d90b713e9d70b98202
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975327"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="fef04-102">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="fef04-102">Defining WCF Data Services</span></span>

<span data-ttu-id="fef04-103">このセクションでは、データを Open Data Protocol (OData) フィードとして公開する WCF Data Services を作成および構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-103">This section describes how to create and configure WCF Data Services to expose data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="fef04-104">データサービスの作成に必要な基本的な手順の詳細については、「[データをサービスとして公開](exposing-your-data-as-a-service-wcf-data-services.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fef04-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fef04-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fef04-105">In This Section</span></span>

 [<span data-ttu-id="fef04-106">データ サービスの構成</span><span class="sxs-lookup"><span data-stu-id="fef04-106">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="fef04-107">WCF Data Services によって提供されるデータサービス構成オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="fef04-108">Data Services プロバイダー</span><span class="sxs-lookup"><span data-stu-id="fef04-108">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="fef04-109">データ サービスとしてデータを公開するプロバイダー モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="fef04-110">サービス操作</span><span class="sxs-lookup"><span data-stu-id="fef04-110">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="fef04-111">サーバー上でメソッドを公開するサービス操作を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="fef04-112">フィードのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fef04-112">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="fef04-113">データ サービス プロバイダーおよびデータ フィードの要素によって定義されるデータ モデルのエンティティ間のマッピングを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="fef04-114">インターセプター</span><span class="sxs-lookup"><span data-stu-id="fef04-114">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="fef04-115">インターセプター メソッドを定義してデータ サービスへの要求に対してカスタム ビジネス ロジックを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="fef04-116">WCF Data Services の開発と配置</span><span class="sxs-lookup"><span data-stu-id="fef04-116">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="fef04-117">Visual Studio を使用してデータ サービスを開発および配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="fef04-118">WCF Data Services のセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="fef04-118">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="fef04-119">データ サービスの認証と承認およびセキュリティに関するその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="fef04-120">データ サービスのホスティング</span><span class="sxs-lookup"><span data-stu-id="fef04-120">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="fef04-121">データ サービスのホストを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="fef04-122">データ サービスのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="fef04-122">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="fef04-123">OData のさまざまなバージョンを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="fef04-124">WCF Data Services プロトコル実装の詳細</span><span class="sxs-lookup"><span data-stu-id="fef04-124">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="fef04-125">WCF Data Services によって現在実装されていない OData プロトコルのオプション機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="fef04-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef04-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="fef04-126">See also</span></span>

- [<span data-ttu-id="fef04-127">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="fef04-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="fef04-128">データ サービス リソースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fef04-128">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="fef04-129">はじめに</span><span class="sxs-lookup"><span data-stu-id="fef04-129">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
