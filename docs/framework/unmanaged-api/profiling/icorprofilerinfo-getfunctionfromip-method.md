---
title: ICorProfilerInfo::GetFunctionFromIP メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 339c5db1610a3cf087085ce19fc663436d9c4ec1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498311"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="c37f4-102">ICorProfilerInfo::GetFunctionFromIP メソッド</span><span class="sxs-lookup"><span data-stu-id="c37f4-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="c37f4-103">マネージコード命令ポインターをにマップ `FunctionID` します。</span><span class="sxs-lookup"><span data-stu-id="c37f4-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c37f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37f4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c37f4-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="c37f4-106">\[in) マネージコード内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="c37f4-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="c37f4-107">\[out] 返された関数 ID。</span><span class="sxs-lookup"><span data-stu-id="c37f4-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="c37f4-108">要件</span><span class="sxs-lookup"><span data-stu-id="c37f4-108">Requirements</span></span>  
 <span data-ttu-id="c37f4-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c37f4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37f4-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c37f4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c37f4-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c37f4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c37f4-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37f4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37f4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c37f4-113">See also</span></span>

- [<span data-ttu-id="c37f4-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c37f4-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
