---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781850"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="33658-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="33658-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="33658-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="33658-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33658-104">ID</span><span class="sxs-lookup"><span data-stu-id="33658-104">ID</span></span>|<span data-ttu-id="33658-105">212</span><span class="sxs-lookup"><span data-stu-id="33658-105">212</span></span>|  
|<span data-ttu-id="33658-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="33658-106">Keywords</span></span>|<span data-ttu-id="33658-107">Troubleshooting、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="33658-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="33658-108">レベル</span><span class="sxs-lookup"><span data-stu-id="33658-108">Level</span></span>|<span data-ttu-id="33658-109">情報</span><span class="sxs-lookup"><span data-stu-id="33658-109">Information</span></span>|  
|<span data-ttu-id="33658-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="33658-110">Channel</span></span>|<span data-ttu-id="33658-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="33658-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33658-112">説明</span><span class="sxs-lookup"><span data-stu-id="33658-112">Description</span></span>  
 <span data-ttu-id="33658-113">このイベントは、Service Model が `BeforeCall` メソッドを `ParameterInspector` で呼び出した後に生成されます。</span><span class="sxs-lookup"><span data-stu-id="33658-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33658-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="33658-114">Message</span></span>  
 <span data-ttu-id="33658-115">ディスパッチャーが型 '%1' の ParameterInspector で 'BeforeCall' を呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="33658-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33658-116">説明</span><span class="sxs-lookup"><span data-stu-id="33658-116">Details</span></span>  
  
|<span data-ttu-id="33658-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="33658-117">Data Item Name</span></span>|<span data-ttu-id="33658-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="33658-118">Data Item Type</span></span>|<span data-ttu-id="33658-119">説明</span><span class="sxs-lookup"><span data-stu-id="33658-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33658-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="33658-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="33658-121">呼び出されたインスペクターの型の CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="33658-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="33658-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="33658-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="33658-123">Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="33658-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="33658-124">その形式が定義されている ' Web サイト名アプリケーション仮想パス&#124;サービス仮想パス&#124;ServiceName'。</span><span class="sxs-lookup"><span data-stu-id="33658-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="33658-125">例:' 既定の Web サイト/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'。</span><span class="sxs-lookup"><span data-stu-id="33658-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="33658-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="33658-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="33658-127">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="33658-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
