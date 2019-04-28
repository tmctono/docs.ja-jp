---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774934"
---
# <a name="499---transferemitted"></a><span data-ttu-id="30e9a-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="30e9a-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="30e9a-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="30e9a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30e9a-104">ID</span><span class="sxs-lookup"><span data-stu-id="30e9a-104">ID</span></span>|<span data-ttu-id="30e9a-105">499</span><span class="sxs-lookup"><span data-stu-id="30e9a-105">499</span></span>|  
|<span data-ttu-id="30e9a-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="30e9a-106">Keywords</span></span>|<span data-ttu-id="30e9a-107">Troubleshooting、UserEvents、EndToEndMonitoring、ServiceModel、WFTracking、ServiceHost、WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="30e9a-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="30e9a-108">レベル</span><span class="sxs-lookup"><span data-stu-id="30e9a-108">Level</span></span>|<span data-ttu-id="30e9a-109">LogAlways (常にログ)</span><span class="sxs-lookup"><span data-stu-id="30e9a-109">LogAlways</span></span>|  
|<span data-ttu-id="30e9a-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="30e9a-110">Channel</span></span>|<span data-ttu-id="30e9a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="30e9a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30e9a-112">説明</span><span class="sxs-lookup"><span data-stu-id="30e9a-112">Description</span></span>  
 <span data-ttu-id="30e9a-113">このイベントは、転送イベントが発生したときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="30e9a-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30e9a-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="30e9a-114">Message</span></span>  
 <span data-ttu-id="30e9a-115">転送イベントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="30e9a-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30e9a-116">説明</span><span class="sxs-lookup"><span data-stu-id="30e9a-116">Details</span></span>  
  
|<span data-ttu-id="30e9a-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="30e9a-117">Data Item Name</span></span>|<span data-ttu-id="30e9a-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="30e9a-118">Data Item Type</span></span>|<span data-ttu-id="30e9a-119">説明</span><span class="sxs-lookup"><span data-stu-id="30e9a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30e9a-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="30e9a-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="30e9a-121">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="30e9a-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="30e9a-122">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="30e9a-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="30e9a-123">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="30e9a-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="30e9a-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30e9a-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="30e9a-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="30e9a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
