---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: cf4a455d80a1a0ac09e99bad967c1feba3653842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596538"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="aefc4-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="aefc4-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="aefc4-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aefc4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aefc4-104">ID</span><span class="sxs-lookup"><span data-stu-id="aefc4-104">ID</span></span>|<span data-ttu-id="aefc4-105">223</span><span class="sxs-lookup"><span data-stu-id="aefc4-105">223</span></span>|  
|<span data-ttu-id="aefc4-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="aefc4-106">Keywords</span></span>|<span data-ttu-id="aefc4-107">EndToEndMonitoring、HealthMonitoring、Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aefc4-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aefc4-108">レベル</span><span class="sxs-lookup"><span data-stu-id="aefc4-108">Level</span></span>|<span data-ttu-id="aefc4-109">警告</span><span class="sxs-lookup"><span data-stu-id="aefc4-109">Warning</span></span>|  
|<span data-ttu-id="aefc4-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="aefc4-110">Channel</span></span>|<span data-ttu-id="aefc4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aefc4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aefc4-112">説明</span><span class="sxs-lookup"><span data-stu-id="aefc4-112">Description</span></span>  
 <span data-ttu-id="aefc4-113">このイベントは、サービス モデルの既定の `OperationInvoker` が、そのメソッドを呼び出している間に `FaultException` から派生する例外に遭遇すると生成されます。</span><span class="sxs-lookup"><span data-stu-id="aefc4-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aefc4-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="aefc4-114">Message</span></span>  
 <span data-ttu-id="aefc4-115">OperationInvoker によって呼び出されたメソッド '%1' で FaultException がスローされました。</span><span class="sxs-lookup"><span data-stu-id="aefc4-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="aefc4-116">メソッド呼び出し時間は '%2' ミリ秒でした。</span><span class="sxs-lookup"><span data-stu-id="aefc4-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aefc4-117">説明</span><span class="sxs-lookup"><span data-stu-id="aefc4-117">Details</span></span>  
  
|<span data-ttu-id="aefc4-118">データ項目名</span><span class="sxs-lookup"><span data-stu-id="aefc4-118">Data Item Name</span></span>|<span data-ttu-id="aefc4-119">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="aefc4-119">Data Item Type</span></span>|<span data-ttu-id="aefc4-120">説明</span><span class="sxs-lookup"><span data-stu-id="aefc4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aefc4-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="aefc4-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="aefc4-122">`OperationInvoker` によって呼び出されたメソッドの CLR 名。</span><span class="sxs-lookup"><span data-stu-id="aefc4-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="aefc4-123">存続期間</span><span class="sxs-lookup"><span data-stu-id="aefc4-123">Duration</span></span>|`xs:long`|<span data-ttu-id="aefc4-124">`OperationInvoker` でメソッドを呼び出すのにかかった時間 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="aefc4-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="aefc4-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="aefc4-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="aefc4-126">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="aefc4-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aefc4-127">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="aefc4-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aefc4-128">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="aefc4-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aefc4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aefc4-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aefc4-130">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="aefc4-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
