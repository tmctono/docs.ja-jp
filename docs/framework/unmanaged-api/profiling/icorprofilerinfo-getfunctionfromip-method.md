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
ms.openlocfilehash: cd1f3982fe1439135bf96579370a5a798c61dd2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863791"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="21c75-102">ICorProfilerInfo::GetFunctionFromIP メソッド</span><span class="sxs-lookup"><span data-stu-id="21c75-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="21c75-103">マネージコード命令ポインターを `FunctionID`にマップします。</span><span class="sxs-lookup"><span data-stu-id="21c75-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c75-104">構文</span><span class="sxs-lookup"><span data-stu-id="21c75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21c75-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21c75-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="21c75-106">in] マネージコード内の命令ポインターを \[します。</span><span class="sxs-lookup"><span data-stu-id="21c75-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="21c75-107">\[出力] 返された関数 ID。</span><span class="sxs-lookup"><span data-stu-id="21c75-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="21c75-108">要件</span><span class="sxs-lookup"><span data-stu-id="21c75-108">Requirements</span></span>  
 <span data-ttu-id="21c75-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c75-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21c75-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21c75-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21c75-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21c75-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21c75-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21c75-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c75-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="21c75-113">See also</span></span>

- [<span data-ttu-id="21c75-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21c75-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
