---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662823"
---
# <a name="activitytransfer"></a><span data-ttu-id="90730-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="90730-102">ActivityTransfer</span></span>
<span data-ttu-id="90730-103">アクティビティ転送イベント</span><span class="sxs-lookup"><span data-stu-id="90730-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90730-104">構文</span><span class="sxs-lookup"><span data-stu-id="90730-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="90730-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="90730-105">Methods</span></span>  
 <span data-ttu-id="90730-106">ActivityTransfer クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="90730-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="90730-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90730-107">Properties</span></span>  
 <span data-ttu-id="90730-108">ActivityTransfer クラスには次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="90730-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="90730-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="90730-109">ActivityID</span></span>  
  
- <span data-ttu-id="90730-110">データ型: object</span><span class="sxs-lookup"><span data-stu-id="90730-110">Data type: object</span></span>  
    <span data-ttu-id="90730-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="90730-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="90730-112">アクティビティ ID</span><span class="sxs-lookup"><span data-stu-id="90730-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="90730-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="90730-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="90730-114">データ型: object</span><span class="sxs-lookup"><span data-stu-id="90730-114">Data type: object</span></span>  
    <span data-ttu-id="90730-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="90730-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="90730-116">関連アクティビティ ID</span><span class="sxs-lookup"><span data-stu-id="90730-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90730-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="90730-117">Requirements</span></span>  
  
|<span data-ttu-id="90730-118">MOF</span><span class="sxs-lookup"><span data-stu-id="90730-118">MOF</span></span>|<span data-ttu-id="90730-119">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="90730-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="90730-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="90730-120">Namespace</span></span>|<span data-ttu-id="90730-121">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="90730-121">Defined in root\ServiceModel.</span></span>|
