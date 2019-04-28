---
title: 301 - UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 6eb80d6f0b20af9aae6e7de5248323088e352b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596480"
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="9856a-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="9856a-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="9856a-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9856a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9856a-104">ID</span><span class="sxs-lookup"><span data-stu-id="9856a-104">ID</span></span>|<span data-ttu-id="9856a-105">301</span><span class="sxs-lookup"><span data-stu-id="9856a-105">301</span></span>|  
|<span data-ttu-id="9856a-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="9856a-106">Keywords</span></span>|<span data-ttu-id="9856a-107">Troubleshooting、HealthMonitoring、UserEvents、ServiceModel、EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="9856a-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="9856a-108">レベル</span><span class="sxs-lookup"><span data-stu-id="9856a-108">Level</span></span>|<span data-ttu-id="9856a-109">Error</span><span class="sxs-lookup"><span data-stu-id="9856a-109">Error</span></span>|  
|<span data-ttu-id="9856a-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="9856a-110">Channel</span></span>|<span data-ttu-id="9856a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9856a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9856a-112">説明</span><span class="sxs-lookup"><span data-stu-id="9856a-112">Description</span></span>  
 <span data-ttu-id="9856a-113">このイベントは、ユーザー コードから生成されます。</span><span class="sxs-lookup"><span data-stu-id="9856a-113">This event is emitted from user code.</span></span> <span data-ttu-id="9856a-114">開発者は、カスタム定義のエラー イベントがサービスで発生したときに、このイベントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="9856a-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="9856a-115">これは、<xref:System.Diagnostics.Eventing> API を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="9856a-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="9856a-116">また、その API をラップし、このイベントを適切に生成する方法を示す、WCF サンプルもあります。</span><span class="sxs-lookup"><span data-stu-id="9856a-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9856a-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9856a-117">Message</span></span>  
 <span data-ttu-id="9856a-118">名前:'%1'、参照:'%2'、ペイロード:%3</span><span class="sxs-lookup"><span data-stu-id="9856a-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="9856a-119">説明</span><span class="sxs-lookup"><span data-stu-id="9856a-119">Details</span></span>  
  
|<span data-ttu-id="9856a-120">データ項目名</span><span class="sxs-lookup"><span data-stu-id="9856a-120">Data Item Name</span></span>|<span data-ttu-id="9856a-121">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="9856a-121">Data Item Type</span></span>|<span data-ttu-id="9856a-122">説明</span><span class="sxs-lookup"><span data-stu-id="9856a-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9856a-123">名前</span><span class="sxs-lookup"><span data-stu-id="9856a-123">Name</span></span>|`xs:string`|<span data-ttu-id="9856a-124">イベントのユーザー定義名。</span><span class="sxs-lookup"><span data-stu-id="9856a-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="9856a-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9856a-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="9856a-126">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="9856a-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9856a-127">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="9856a-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9856a-128">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="9856a-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9856a-129">Payload</span><span class="sxs-lookup"><span data-stu-id="9856a-129">Payload</span></span>|`xs:string`|<span data-ttu-id="9856a-130">イベントのユーザー定義ペイロード。</span><span class="sxs-lookup"><span data-stu-id="9856a-130">The user-defined payload of the event.</span></span>|
