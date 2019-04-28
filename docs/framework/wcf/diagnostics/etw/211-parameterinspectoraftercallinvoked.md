---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781863"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="badfa-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="badfa-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="badfa-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="badfa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="badfa-104">ID</span><span class="sxs-lookup"><span data-stu-id="badfa-104">ID</span></span>|<span data-ttu-id="badfa-105">211</span><span class="sxs-lookup"><span data-stu-id="badfa-105">211</span></span>|  
|<span data-ttu-id="badfa-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="badfa-106">Keywords</span></span>|<span data-ttu-id="badfa-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="badfa-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="badfa-108">レベル</span><span class="sxs-lookup"><span data-stu-id="badfa-108">Level</span></span>|<span data-ttu-id="badfa-109">情報</span><span class="sxs-lookup"><span data-stu-id="badfa-109">Information</span></span>|  
|<span data-ttu-id="badfa-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="badfa-110">Channel</span></span>|<span data-ttu-id="badfa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="badfa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="badfa-112">説明</span><span class="sxs-lookup"><span data-stu-id="badfa-112">Description</span></span>  
 <span data-ttu-id="badfa-113">このイベントは、Service Model が `AfterCall` メソッドを `ParameterInspector` で呼び出した後に生成されます。</span><span class="sxs-lookup"><span data-stu-id="badfa-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="badfa-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="badfa-114">Message</span></span>  
 <span data-ttu-id="badfa-115">ディスパッチャーが型 '%1' の ParameterInspector で 'AfterCall' を呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="badfa-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="badfa-116">説明</span><span class="sxs-lookup"><span data-stu-id="badfa-116">Details</span></span>  
  
|<span data-ttu-id="badfa-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="badfa-117">Data Item Name</span></span>|<span data-ttu-id="badfa-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="badfa-118">Data Item Type</span></span>|<span data-ttu-id="badfa-119">説明</span><span class="sxs-lookup"><span data-stu-id="badfa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="badfa-120">型の名前</span><span class="sxs-lookup"><span data-stu-id="badfa-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="badfa-121">呼び出された `ParameterInspector` の型の CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="badfa-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="badfa-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="badfa-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="badfa-123">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="badfa-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="badfa-124">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="badfa-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="badfa-125">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="badfa-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="badfa-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="badfa-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="badfa-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="badfa-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
