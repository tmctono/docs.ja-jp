---
title: サービスのサンプルの WCF
ms.date: 03/30/2017
ms.assetid: 462a2218-f8c6-4fb7-95bc-64765459c429
ms.openlocfilehash: 3fbca09a7b50a15299cb8e805ac84c60e4b78fa7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967545"
---
# <a name="services"></a><span data-ttu-id="f062b-102">Services</span><span class="sxs-lookup"><span data-stu-id="f062b-102">Services</span></span>

<span data-ttu-id="f062b-103">このセクションには、Windows Communication Foundation (WCF) サービスを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f062b-103">This section contains samples that demonstrate Windows Communication Foundation (WCF) services.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f062b-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f062b-104">In this section</span></span>

- <span data-ttu-id="f062b-105">[ホスト](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-105">[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span></span>
<span data-ttu-id="f062b-106">WCF サービスのホスティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f062b-106">Demonstrates hosting WCF services.</span></span>

- <span data-ttu-id="f062b-107">[サービス相互運用性](service-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-107">[Service Interoperability](service-interoperability.md)\\</span></span>
<span data-ttu-id="f062b-108">WCF と他のサービス技術間の対話を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-108">Demonstrates interaction between WCF and other service technologies.</span></span>

- <span data-ttu-id="f062b-109">[動作](behaviors.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-109">[Behaviors](behaviors.md)\\</span></span>
<span data-ttu-id="f062b-110">WCF サービスの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f062b-110">Demonstrates WCF service behaviors.</span></span>

- <span data-ttu-id="f062b-111">[サービスのセキュリティ](service-security.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-111">[Service Security](service-security.md)\\</span></span>
<span data-ttu-id="f062b-112">WCF サービスのセキュリティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f062b-112">Demonstrates WCF service security.</span></span>

- <span data-ttu-id="f062b-113">[WCF サービスの簡略化された構成](simplified-configuration-for-wcf-services.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-113">[Simplified Configuration for WCF Services](simplified-configuration-for-wcf-services.md)\\</span></span>
<span data-ttu-id="f062b-114">一般的なサービスおよび WCF を使用してクライアントを実装して構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-114">Demonstrates how to implement and configure a typical service and client using WCF.</span></span>

- <span data-ttu-id="f062b-115">[標準エンドポイントの使用](usage-of-standard-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-115">[Usage of Standard Endoints](usage-of-standard-endpoints.md)\\</span></span>
<span data-ttu-id="f062b-116">サービスの構成ファイルでの標準エンドポイントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-116">Demonstrates how to use standard endpoints in service configuration files.</span></span>

- <span data-ttu-id="f062b-117">[拡張保護ポリシー](extended-protection-policy.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-117">[Extended Protection Policy](extended-protection-policy.md)\\</span></span>
<span data-ttu-id="f062b-118">man-in-the-middle (MITM) 攻撃に対するセキュリティ イニシアチブである、拡張保護を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-118">Demonstrates Extended Protection, a security initiative for protecting against man-in-the-middle (MITM) attacks.</span></span>

- <span data-ttu-id="f062b-119">[構成チャネル ファクトリ](configuration-channel-factory.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-119">[Configuration Channel Factory](configuration-channel-factory.md)\\</span></span>
<span data-ttu-id="f062b-120"><xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-120">Demonstrates the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span>

- <span data-ttu-id="f062b-121">[アドレス指定](addressing.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-121">[Addressing](addressing.md)\\</span></span>
<span data-ttu-id="f062b-122">エンドポイント アドレスのさまざまな特性と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-122">Demonstrates various aspects and features of endpoint addresses.</span></span>

- <span data-ttu-id="f062b-123">[命令型](imperative.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-123">[Imperative](imperative.md)\\</span></span>
<span data-ttu-id="f062b-124">コードを使用するサービスについて、構成で <xref:System.ServiceModel.WSHttpBinding> バインディングを定義する代わりに `wsHttpBinding` を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-124">Demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span>

- <span data-ttu-id="f062b-125">[複数のコントラクト](multiple-contracts.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-125">[Multiple Contracts](multiple-contracts.md)\\</span></span>
<span data-ttu-id="f062b-126">複数のコントラクトを 1 つのサービスに実装する方法と、実装された各コントラクトと通信を行うためにエンドポイントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-126">Demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span>

- <span data-ttu-id="f062b-127">[複数のエンドポイント](multiple-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-127">[Multiple Endpoints](multiple-endpoints.md)\\</span></span>
<span data-ttu-id="f062b-128">複数のエンドポイントを 1 つのサービスに構成する方法と、クライアントから各エンドポイントと通信を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-128">Demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span>

- <span data-ttu-id="f062b-129">[単一 ListenUri で複数のエンドポイント](multiple-endpoints-at-a-single-listenuri.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-129">[Multiple Endpoints at a Single ListenUri](multiple-endpoints-at-a-single-listenuri.md)\\</span></span>
<span data-ttu-id="f062b-130">単一 `ListenUri` で複数のエンドポイントをホストするサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-130">Demonstrates a service that hosts multiple endpoints at a single `ListenUri`.</span></span>

- <span data-ttu-id="f062b-131">[OperationContextScope](operationcontextscope.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-131">[OperationContextScope](operationcontextscope.md)\\</span></span>
<span data-ttu-id="f062b-132">ヘッダーを使用して WCF の呼び出しで追加の情報を送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-132">Demonstrates how to send extra information on a WCF call using headers.</span></span>

- <span data-ttu-id="f062b-133">[サービスの説明](service-description.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-133">[Service Description](service-description.md)\\</span></span>
<span data-ttu-id="f062b-134">サービスが実行時にそのサービスの説明情報を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-134">Demonstrates how a service can retrieve its service description information at runtime.</span></span>

- <span data-ttu-id="f062b-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span><span class="sxs-lookup"><span data-stu-id="f062b-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span></span>
<span data-ttu-id="f062b-136">サービス実装で Reentrant コンカレンシー モードを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f062b-136">Demonstrates how to use the Reentrant concurrency mode on a service implementation.</span></span>