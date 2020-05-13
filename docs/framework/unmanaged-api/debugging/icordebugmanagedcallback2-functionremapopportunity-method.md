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
ms.openlocfilehash: d2fc59621cbb6752830c7a8392ce4e0c476ef9e7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210060"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="a2a80-102">ICorDebugManagedCallback2::FunctionRemapOpportunity メソッド</span><span class="sxs-lookup"><span data-stu-id="a2a80-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="a2a80-103">コードの実行が、編集された関数の古いバージョンのシーケンスポイントに達したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a2a80-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a80-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2a80-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a80-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2a80-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a2a80-106">から編集された関数を含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2a80-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="a2a80-107">からリマップブレークポイントが検出されたスレッドを表す、スレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2a80-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="a2a80-108">からスレッドで現在実行されている関数のバージョンを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2a80-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="a2a80-109">から関数の最新バージョンを表す、の関数オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2a80-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="a2a80-110">から以前のバージョンの関数の命令ポインターの MSIL (Microsoft 中間言語) オフセット。</span><span class="sxs-lookup"><span data-stu-id="a2a80-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a80-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2a80-111">Remarks</span></span>  
 <span data-ttu-id="a2a80-112">このコールバックでは、 [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md)メソッドを呼び出すことによって、指定された関数の新しいバージョンの適切な場所に命令ポインターを再マップする機会がデバッガーに与えられます。</span><span class="sxs-lookup"><span data-stu-id="a2a80-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="a2a80-113">場合、デバッガーは、 `RemapFunction` 次のシーケンスポイント[ICorDebugController::Continue](icordebugcontroller-continue-method.md)では、前のコードを実行してから別のコールバックを起動して、このメソッドを呼び出すことができません。 `FunctionRemapOpportunity`</span><span class="sxs-lookup"><span data-stu-id="a2a80-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="a2a80-114">このコールバックは、指定された関数の古いバージョンを実行しているすべてのフレームに対して、デバッガーが S_OK を返すまで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a2a80-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a80-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2a80-115">Requirements</span></span>  
 <span data-ttu-id="a2a80-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2a80-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a80-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2a80-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2a80-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2a80-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2a80-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a80-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a80-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2a80-120">See also</span></span>

- [<span data-ttu-id="a2a80-121">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2a80-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="a2a80-122">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2a80-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
