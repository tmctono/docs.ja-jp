---
title: ICorProfilerInfo2::EnumModuleFrozenObjects メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a325c3e1aa9c08e00dc2cc38e3f7833fa9f99897
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472578"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="db754-102">ICorProfilerInfo2::EnumModuleFrozenObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="db754-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="db754-103">指定したモジュールに固定されたオブジェクトに対して反復処理する列挙子を取得します。このメソッドは廃止されています。</span><span class="sxs-lookup"><span data-stu-id="db754-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db754-104">構文</span><span class="sxs-lookup"><span data-stu-id="db754-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db754-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db754-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="db754-106">[in]列挙する固定オブジェクトを含むモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="db754-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="db754-107">[out]アドレスへのポインター、 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)インターフェイスでは、固定されたオブジェクトを列挙します。</span><span class="sxs-lookup"><span data-stu-id="db754-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db754-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="db754-108">Requirements</span></span>  
 <span data-ttu-id="db754-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db754-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db754-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db754-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db754-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db754-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db754-112">**.NET framework のバージョン:** 3.5、3.0 SP1 では、3.0、2.0 SP1 では、2.0</span><span class="sxs-lookup"><span data-stu-id="db754-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db754-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="db754-113">See also</span></span>
- [<span data-ttu-id="db754-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db754-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="db754-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db754-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
