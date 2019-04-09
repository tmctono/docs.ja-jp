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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23fb9c58f2eac904b63294434654f3caf1ba9f41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107966"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="fd570-102">ICorProfilerInfo::GetFunctionFromIP メソッド</span><span class="sxs-lookup"><span data-stu-id="fd570-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="fd570-103">マネージ コードの命令ポインターのマップを`FunctionID`します。</span><span class="sxs-lookup"><span data-stu-id="fd570-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd570-104">構文</span><span class="sxs-lookup"><span data-stu-id="fd570-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd570-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd570-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="fd570-106">[in]マネージ コードで命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="fd570-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="fd570-107">[out]返される関数の id。</span><span class="sxs-lookup"><span data-stu-id="fd570-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd570-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd570-108">Requirements</span></span>  
 <span data-ttu-id="fd570-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd570-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd570-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd570-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd570-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd570-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fd570-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fd570-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd570-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd570-113">See also</span></span>

- [<span data-ttu-id="fd570-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd570-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
