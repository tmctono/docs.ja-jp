---
title: ICorProfilerInfo3::GetAppDomainsContainingModule メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 120c31b61734cfb4cb0048489632bc0848a9430b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782179"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="2c4d9-102">ICorProfilerInfo3::GetAppDomainsContainingModule メソッド</span><span class="sxs-lookup"><span data-stu-id="2c4d9-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="2c4d9-103">指定したモジュールが読み込まれているアプリケーション ドメインの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c4d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c4d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c4d9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2c4d9-106">[in] 読み込まれたモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="2c4d9-107">[in] `appDomainIds` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="2c4d9-108">[out] 返される要素の総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="2c4d9-109">[out] アプリケーション ドメイン ID 値の配列。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c4d9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c4d9-110">Remarks</span></span>  
 <span data-ttu-id="2c4d9-111">このメソッドは、呼び出し元が割り当てたバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c4d9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c4d9-112">Requirements</span></span>  
 <span data-ttu-id="2c4d9-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c4d9-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c4d9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c4d9-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c4d9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c4d9-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4d9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c4d9-117">See also</span></span>

- [<span data-ttu-id="2c4d9-118">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c4d9-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="2c4d9-119">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c4d9-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="2c4d9-120">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c4d9-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="2c4d9-121">プロファイル</span><span class="sxs-lookup"><span data-stu-id="2c4d9-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
