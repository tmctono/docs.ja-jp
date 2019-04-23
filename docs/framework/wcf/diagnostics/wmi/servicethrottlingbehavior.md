---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771774"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="4ef33-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="4ef33-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="4ef33-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="4ef33-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef33-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ef33-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4ef33-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4ef33-105">Methods</span></span>  
 <span data-ttu-id="4ef33-106">ServiceThrottlingBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="4ef33-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4ef33-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4ef33-107">Properties</span></span>  
 <span data-ttu-id="4ef33-108">ServiceThrottlingBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4ef33-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="4ef33-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="4ef33-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="4ef33-110">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="4ef33-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4ef33-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4ef33-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4ef33-112">ServiceHost 内のすべてのディスパッチャー オブジェクトでアクティブに処理中のメッセージの最大数。</span><span class="sxs-lookup"><span data-stu-id="4ef33-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="4ef33-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="4ef33-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="4ef33-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="4ef33-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="4ef33-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4ef33-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4ef33-116">一度に実行可能なサービス オブジェクトの最大数。</span><span class="sxs-lookup"><span data-stu-id="4ef33-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="4ef33-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="4ef33-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="4ef33-118">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="4ef33-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4ef33-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="4ef33-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4ef33-120">ホストが一度に受け入れ可能なセッションの最大数。</span><span class="sxs-lookup"><span data-stu-id="4ef33-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ef33-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="4ef33-121">Requirements</span></span>  
  
|<span data-ttu-id="4ef33-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4ef33-122">MOF</span></span>|<span data-ttu-id="4ef33-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="4ef33-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4ef33-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="4ef33-124">Namespace</span></span>|<span data-ttu-id="4ef33-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="4ef33-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ef33-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ef33-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
