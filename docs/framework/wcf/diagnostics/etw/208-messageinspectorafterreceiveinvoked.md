---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781902"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="f473d-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="f473d-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f473d-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f473d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f473d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f473d-104">ID</span></span>|<span data-ttu-id="f473d-105">208</span><span class="sxs-lookup"><span data-stu-id="f473d-105">208</span></span>|  
|<span data-ttu-id="f473d-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="f473d-106">Keywords</span></span>|<span data-ttu-id="f473d-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f473d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f473d-108">レベル</span><span class="sxs-lookup"><span data-stu-id="f473d-108">Level</span></span>|<span data-ttu-id="f473d-109">情報</span><span class="sxs-lookup"><span data-stu-id="f473d-109">Information</span></span>|  
|<span data-ttu-id="f473d-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="f473d-110">Channel</span></span>|<span data-ttu-id="f473d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f473d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f473d-112">説明</span><span class="sxs-lookup"><span data-stu-id="f473d-112">Description</span></span>  
 <span data-ttu-id="f473d-113">このイベントは、メッセージ インスペクターで Service Model が `AfterReceive` メソッドを呼び出した後に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f473d-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f473d-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="f473d-114">Message</span></span>  
 <span data-ttu-id="f473d-115">ディスパッチャーが型 '%1' の MessageInspector で 'AfterReceiveReply' を呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="f473d-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f473d-116">説明</span><span class="sxs-lookup"><span data-stu-id="f473d-116">Details</span></span>  
  
|<span data-ttu-id="f473d-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="f473d-117">Data Item Name</span></span>|<span data-ttu-id="f473d-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="f473d-118">Data Item Type</span></span>|<span data-ttu-id="f473d-119">説明</span><span class="sxs-lookup"><span data-stu-id="f473d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f473d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f473d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f473d-121">呼び出された `MessageInspector` の型の CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="f473d-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="f473d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f473d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f473d-123">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="f473d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f473d-124">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="f473d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f473d-125">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="f473d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f473d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f473d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f473d-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="f473d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
