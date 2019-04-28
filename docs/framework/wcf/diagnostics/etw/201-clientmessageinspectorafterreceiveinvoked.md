---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782039"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="b0c69-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="b0c69-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b0c69-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b0c69-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0c69-104">ID</span><span class="sxs-lookup"><span data-stu-id="b0c69-104">ID</span></span>|<span data-ttu-id="b0c69-105">201</span><span class="sxs-lookup"><span data-stu-id="b0c69-105">201</span></span>|  
|<span data-ttu-id="b0c69-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="b0c69-106">Keywords</span></span>|<span data-ttu-id="b0c69-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b0c69-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b0c69-108">レベル</span><span class="sxs-lookup"><span data-stu-id="b0c69-108">Level</span></span>|<span data-ttu-id="b0c69-109">情報</span><span class="sxs-lookup"><span data-stu-id="b0c69-109">Information</span></span>|  
|<span data-ttu-id="b0c69-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="b0c69-110">Channel</span></span>|<span data-ttu-id="b0c69-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b0c69-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b0c69-112">説明</span><span class="sxs-lookup"><span data-stu-id="b0c69-112">Description</span></span>  
 <span data-ttu-id="b0c69-113">このイベントは、クライアント メッセージ インスペクターで Service Model が `AfterReceiveReply` メソッドを呼び出した後に生成されます。</span><span class="sxs-lookup"><span data-stu-id="b0c69-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b0c69-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="b0c69-114">Message</span></span>  
 <span data-ttu-id="b0c69-115">ディスパッチャーが型 '%1' の ClientMessageInspector で 'AfterReceiveReply' を呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="b0c69-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b0c69-116">説明</span><span class="sxs-lookup"><span data-stu-id="b0c69-116">Details</span></span>  
  
|<span data-ttu-id="b0c69-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="b0c69-117">Data Item Name</span></span>|<span data-ttu-id="b0c69-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="b0c69-118">Data Item Type</span></span>|<span data-ttu-id="b0c69-119">説明</span><span class="sxs-lookup"><span data-stu-id="b0c69-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b0c69-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="b0c69-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="b0c69-121">呼び出されたインスペクターの型の CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="b0c69-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="b0c69-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="b0c69-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="b0c69-123">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="b0c69-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b0c69-124">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="b0c69-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b0c69-125">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="b0c69-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b0c69-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b0c69-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b0c69-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="b0c69-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
