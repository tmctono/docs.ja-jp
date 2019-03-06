---
title: ICorProfilerInfo::GetInprocInspectionIThisThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bcf52a3745b22df58e67e892bf3a2b77c542d43
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479001"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="ff013-102">ICorProfilerInfo::GetInprocInspectionIThisThread メソッド</span><span class="sxs-lookup"><span data-stu-id="ff013-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="ff013-103">ICorDebugThread インターフェイスのクエリを実行できるオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ff013-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="ff013-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="ff013-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff013-105">構文</span><span class="sxs-lookup"><span data-stu-id="ff013-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff013-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff013-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="ff013-107">[out](/cpp/atl/iunknown)オブジェクトのクエリを実行できる、`ICorDebugThread`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ff013-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff013-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff013-108">Remarks</span></span>  
 <span data-ttu-id="ff013-109">サービスのデバッグ共通言語ランタイム (CLR) では、.NET Framework version 1.0 での限られたインプロセス デバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ff013-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="ff013-110">インプロセス デバッグするには、デバッグ API の検査の部分を使用するプロファイラーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ff013-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="ff013-111">お客様からのフィードバックの結果としてインプロセス デバッグがバージョン 2.0、.NET Framework から削除され、プロファイル API に合わせてさらには、機能のセットに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ff013-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff013-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ff013-112">Requirements</span></span>  
 <span data-ttu-id="ff013-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff013-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff013-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff013-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff013-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff013-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff013-116">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="ff013-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff013-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff013-117">See also</span></span>
- [<span data-ttu-id="ff013-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff013-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
