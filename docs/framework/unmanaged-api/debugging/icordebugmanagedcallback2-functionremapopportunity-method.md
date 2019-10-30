---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: c6c361113a441df050a8e7cd5219819cc8332581
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131487"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="a3c1d-102">ICorDebugManagedCallback2::FunctionRemapOpportunity メソッド</span><span class="sxs-lookup"><span data-stu-id="a3c1d-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="a3c1d-103">コードの実行が、編集された関数の古いバージョンのシーケンスポイントに達したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3c1d-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3c1d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a3c1d-106">から編集された関数を含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="a3c1d-107">からリマップブレークポイントが検出されたスレッドを表す、スレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="a3c1d-108">からスレッドで現在実行されている関数のバージョンを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="a3c1d-109">から関数の最新バージョンを表す、の関数オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="a3c1d-110">から以前のバージョンの関数の命令ポインターの MSIL (Microsoft 中間言語) オフセット。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3c1d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3c1d-111">Remarks</span></span>  
 <span data-ttu-id="a3c1d-112">このコールバックでは、 [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)メソッドを呼び出すことによって、指定された関数の新しいバージョンの適切な場所に命令ポインターを再マップする機会がデバッガーに与えられます。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="a3c1d-113">デバッガーが `RemapFunction` を呼び出さず[に、"](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)を実行する前のコードを呼び出すと、ランタイムは引き続き古いコードを実行し、次のシーケンスポイントで別の `FunctionRemapOpportunity` コールバックを起動します。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="a3c1d-114">このコールバックは、デバッガーが S_OK を返すまで、指定された関数の古いバージョンを実行しているすべてのフレームに対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c1d-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="a3c1d-115">Requirements</span></span>  
 <span data-ttu-id="a3c1d-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3c1d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c1d-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3c1d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3c1d-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3c1d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c1d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c1d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c1d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3c1d-120">See also</span></span>

- [<span data-ttu-id="a3c1d-121">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3c1d-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="a3c1d-122">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3c1d-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
