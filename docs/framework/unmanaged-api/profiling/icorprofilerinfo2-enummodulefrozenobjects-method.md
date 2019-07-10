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
ms.openlocfilehash: 3e044a9dedf96025981c1a77471c6abedfc26420
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762374"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="3cbd2-102">ICorProfilerInfo2::EnumModuleFrozenObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="3cbd2-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="3cbd2-103">指定したモジュールに固定されたオブジェクトに対して反復処理する列挙子を取得します。このメソッドは廃止されています。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbd2-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cbd2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cbd2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cbd2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="3cbd2-106">[in]列挙する固定オブジェクトを含むモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="3cbd2-107">[out]アドレスへのポインター、 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)インターフェイスでは、固定されたオブジェクトを列挙します。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cbd2-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="3cbd2-108">Requirements</span></span>  
 <span data-ttu-id="3cbd2-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbd2-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3cbd2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3cbd2-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cbd2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cbd2-112">**.NET framework のバージョン:** 3.5、3.0 SP1 では、3.0、2.0 SP1 では、2.0</span><span class="sxs-lookup"><span data-stu-id="3cbd2-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbd2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cbd2-113">See also</span></span>

- [<span data-ttu-id="3cbd2-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cbd2-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3cbd2-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cbd2-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
