---
title: ICorProfilerInfo::GetInprocInspectionInterface メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbb4aa43757df86037d9c883e76ee38cef5eeb86
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494429"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="47f2d-102">ICorProfilerInfo::GetInprocInspectionInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="47f2d-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="47f2d-103">"ICorDebugProcess"インターフェイスのクエリを実行できるオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="47f2d-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="47f2d-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="47f2d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f2d-105">構文</span><span class="sxs-lookup"><span data-stu-id="47f2d-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47f2d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47f2d-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="47f2d-107">[out](/cpp/atl/iunknown)オブジェクトのクエリを実行できる、`ICorDebugProcess`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="47f2d-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47f2d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="47f2d-108">Remarks</span></span>  
 <span data-ttu-id="47f2d-109">デバッグ API 共通言語ランタイム (CLR) では、.NET Framework version 1.0 での限られたインプロセス デバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47f2d-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="47f2d-110">インプロセス デバッグするには、デバッグ API の検査の部分を使用するプロファイラーを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="47f2d-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="47f2d-111">お客様からのフィードバックの結果としてインプロセス デバッグがバージョン 2.0、.NET Framework から削除され、プロファイル API に合わせてさらには、機能のセットに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="47f2d-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f2d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="47f2d-112">Requirements</span></span>  
 <span data-ttu-id="47f2d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f2d-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47f2d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47f2d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47f2d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47f2d-116">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="47f2d-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f2d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="47f2d-117">See also</span></span>
- [<span data-ttu-id="47f2d-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47f2d-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
