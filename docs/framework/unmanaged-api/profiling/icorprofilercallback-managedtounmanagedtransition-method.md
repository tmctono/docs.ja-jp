---
title: ICorProfilerCallback::ManagedToUnmanagedTransition メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b00394d0b08e7e4a02b95437908dd65a51d0a042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597675"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="d932c-102">ICorProfilerCallback::ManagedToUnmanagedTransition メソッド</span><span class="sxs-lookup"><span data-stu-id="d932c-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="d932c-103">マネージ コードからアンマネージ コードへの移行が発生したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d932c-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d932c-104">構文</span><span class="sxs-lookup"><span data-stu-id="d932c-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d932c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d932c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d932c-106">[in]呼び出される関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d932c-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="d932c-107">[in]値、 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 、マネージ コードからアンマネージ コードへの呼び出しによって、またはアンマネージによって呼び出されるマネージ関数の戻り値のために、移行が発生したかどうかを示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="d932c-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d932c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d932c-108">Remarks</span></span>  
 <span data-ttu-id="d932c-109">場合の値`reason`COR_PRF_TRANSITION_CALL、こと、アンマネージ関数は決してコンパイルされたジャスト イン タイム コンパイラを使用して ID は、関数は、します。</span><span class="sxs-lookup"><span data-stu-id="d932c-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="d932c-110">アンマネージ関数では、名前といくつかのメタデータなど、それに関連付けられている基本情報があります。</span><span class="sxs-lookup"><span data-stu-id="d932c-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="d932c-111">暗黙的なプラットフォームを使用して、アンマネージ関数が呼び出された場合は、呼び出し (PInvoke)、ランタイムは、呼び出しの変換先およびの値を判別できません`functionId`は null になります。</span><span class="sxs-lookup"><span data-stu-id="d932c-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="d932c-112">詳細については、暗黙の PInvoke は、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)します。</span><span class="sxs-lookup"><span data-stu-id="d932c-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d932c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="d932c-113">Requirements</span></span>  
 <span data-ttu-id="d932c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d932c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d932c-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d932c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d932c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d932c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d932c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d932c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d932c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d932c-118">See also</span></span>

- [<span data-ttu-id="d932c-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d932c-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d932c-120">UnmanagedToManagedTransition メソッド</span><span class="sxs-lookup"><span data-stu-id="d932c-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="d932c-121">C++ での明示的な PInvoke (DllImport 属性) の使用方法</span><span class="sxs-lookup"><span data-stu-id="d932c-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
