---
title: ICorProfilerCallback::UnmanagedToManagedTransition メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 312f133c263becfd815f1b4ad48dff4892963aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041783"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="99f87-102">ICorProfilerCallback::UnmanagedToManagedTransition メソッド</span><span class="sxs-lookup"><span data-stu-id="99f87-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="99f87-103">アンマネージ コードからマネージ コードへの移行が発生したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="99f87-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f87-104">構文</span><span class="sxs-lookup"><span data-stu-id="99f87-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f87-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99f87-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="99f87-106">[in]呼び出される関数の ID。</span><span class="sxs-lookup"><span data-stu-id="99f87-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="99f87-107">[in]値、 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 、アンマネージ コードからマネージ コードへの呼び出しによって、または管理対象の 1 つによって呼び出される非管理対象の関数の戻り値のために、移行が発生したかどうかを示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="99f87-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99f87-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="99f87-108">Remarks</span></span>  
 <span data-ttu-id="99f87-109">場合の値`reason`は COR_PRF_TRANSITION_RETURN と`functionId`が null でない ID が非管理対象の関数とは決してがコンパイルされました - イン タイム (JIT) コンパイラを使用して関数。</span><span class="sxs-lookup"><span data-stu-id="99f87-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="99f87-110">アンマネージ関数では、名前といくつかのメタデータなど、それに関連付けられているいくつかの基本的な情報があります。</span><span class="sxs-lookup"><span data-stu-id="99f87-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="99f87-111">場合の値`reason`COR_PRF_TRANSITION_CALL には、呼び出された関数 (つまり、マネージ関数) されていない JIT コンパイルされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99f87-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f87-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="99f87-112">Requirements</span></span>  
 <span data-ttu-id="99f87-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99f87-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f87-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99f87-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99f87-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99f87-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99f87-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f87-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f87-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="99f87-117">See also</span></span>

- [<span data-ttu-id="99f87-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="99f87-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="99f87-119">ManagedToUnmanagedTransition メソッド</span><span class="sxs-lookup"><span data-stu-id="99f87-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="99f87-120">C++ での明示的な PInvoke (DllImport 属性) の使用方法</span><span class="sxs-lookup"><span data-stu-id="99f87-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="99f87-121">C++ Interop (暗黙の PInvoke) の使用</span><span class="sxs-lookup"><span data-stu-id="99f87-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
