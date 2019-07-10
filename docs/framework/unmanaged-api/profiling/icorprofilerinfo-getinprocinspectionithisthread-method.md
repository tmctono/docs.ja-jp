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
ms.openlocfilehash: 3e0f56dd6ece32b1f05418ea288da409af5cad5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782758"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="a77b8-102">ICorProfilerInfo::GetInprocInspectionIThisThread メソッド</span><span class="sxs-lookup"><span data-stu-id="a77b8-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="a77b8-103">ICorDebugThread インターフェイスのクエリを実行できるオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a77b8-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="a77b8-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="a77b8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77b8-105">構文</span><span class="sxs-lookup"><span data-stu-id="a77b8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a77b8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a77b8-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="a77b8-107">[out](/cpp/atl/iunknown)オブジェクトのクエリを実行できる、`ICorDebugThread`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a77b8-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a77b8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a77b8-108">Remarks</span></span>  
 <span data-ttu-id="a77b8-109">サービスのデバッグ共通言語ランタイム (CLR) では、.NET Framework version 1.0 での限られたインプロセス デバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a77b8-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="a77b8-110">インプロセス デバッグするには、デバッグ API の検査の部分を使用するプロファイラーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a77b8-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="a77b8-111">お客様からのフィードバックの結果としてインプロセス デバッグがバージョン 2.0、.NET Framework から削除され、プロファイル API に合わせてさらには、機能のセットに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a77b8-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a77b8-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a77b8-112">Requirements</span></span>  
 <span data-ttu-id="a77b8-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a77b8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a77b8-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a77b8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a77b8-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a77b8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a77b8-116">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="a77b8-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77b8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a77b8-117">See also</span></span>

- [<span data-ttu-id="a77b8-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a77b8-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
