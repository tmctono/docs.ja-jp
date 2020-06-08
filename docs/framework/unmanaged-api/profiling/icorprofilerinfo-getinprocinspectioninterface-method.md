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
ms.openlocfilehash: 2fe0b314f761cf3c7a3a926d40c69302d0ece000
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498090"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="afe0e-102">ICorProfilerInfo::GetInprocInspectionInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="afe0e-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="afe0e-103">"いいプロセス" インターフェイスに対してクエリを実行できるオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="afe0e-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="afe0e-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="afe0e-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe0e-105">構文</span><span class="sxs-lookup"><span data-stu-id="afe0e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afe0e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afe0e-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="afe0e-107">インターフェイスに対してクエリを実行できる[out](/cpp/atl/iunknown)オブジェクト `ICorDebugProcess` 。</span><span class="sxs-lookup"><span data-stu-id="afe0e-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afe0e-108">解説</span><span class="sxs-lookup"><span data-stu-id="afe0e-108">Remarks</span></span>  
 <span data-ttu-id="afe0e-109">共通言語ランタイム (CLR) デバッグ API でサポートされている .NET Framework バージョン1.0 では、プロセス内デバッグが制限されています。</span><span class="sxs-lookup"><span data-stu-id="afe0e-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="afe0e-110">インプロセスデバッグでは、デバッグ API の検査部分を使用するプロファイラーが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="afe0e-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="afe0e-111">お客様からのフィードバックの結果として、プロセス内デバッグはバージョン2.0 の .NET Framework から削除され、プロファイル API により多くの機能を備えた一連の機能に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="afe0e-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afe0e-112">要件</span><span class="sxs-lookup"><span data-stu-id="afe0e-112">Requirements</span></span>  
 <span data-ttu-id="afe0e-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe0e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afe0e-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="afe0e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="afe0e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afe0e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afe0e-116">**.NET Framework のバージョン:** 1.0</span><span class="sxs-lookup"><span data-stu-id="afe0e-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe0e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="afe0e-117">See also</span></span>

- [<span data-ttu-id="afe0e-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afe0e-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
