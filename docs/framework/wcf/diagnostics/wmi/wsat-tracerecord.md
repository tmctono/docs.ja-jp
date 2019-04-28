---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923410"
---
# <a name="wsattracerecord"></a><span data-ttu-id="641fe-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="641fe-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="641fe-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="641fe-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="641fe-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="641fe-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="641fe-105">Methods</span></span>  
 <span data-ttu-id="641fe-106">WSAT_TraceRecord クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="641fe-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="641fe-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="641fe-107">Properties</span></span>  
 <span data-ttu-id="641fe-108">WSAT_TraceRecord クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="641fe-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="641fe-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="641fe-109">ActivityID</span></span>  
 <span data-ttu-id="641fe-110">データ型: object</span><span class="sxs-lookup"><span data-stu-id="641fe-110">Data type: object</span></span>  
<span data-ttu-id="641fe-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="641fe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641fe-112">トレース レコードのアクティビティ ID です。</span><span class="sxs-lookup"><span data-stu-id="641fe-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="641fe-113">EventID</span><span class="sxs-lookup"><span data-stu-id="641fe-113">EventID</span></span>  
 <span data-ttu-id="641fe-114">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="641fe-114">Data type: sint32</span></span>  
<span data-ttu-id="641fe-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="641fe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641fe-116">トレース レコードのイベント ID です。</span><span class="sxs-lookup"><span data-stu-id="641fe-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="641fe-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="641fe-117">TraceRecord</span></span>  
 <span data-ttu-id="641fe-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="641fe-118">Data type: string</span></span>  
<span data-ttu-id="641fe-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="641fe-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641fe-120">トレース レコード</span><span class="sxs-lookup"><span data-stu-id="641fe-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="641fe-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="641fe-121">Requirements</span></span>  
  
|<span data-ttu-id="641fe-122">MOF</span><span class="sxs-lookup"><span data-stu-id="641fe-122">MOF</span></span>|<span data-ttu-id="641fe-123">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="641fe-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="641fe-124">名前空間</span><span class="sxs-lookup"><span data-stu-id="641fe-124">Namespace</span></span>|<span data-ttu-id="641fe-125">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="641fe-125">Defined in root\ServiceModel</span></span>|
