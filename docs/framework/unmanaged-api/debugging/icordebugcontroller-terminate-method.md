---
title: ICorDebugController::Terminate メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125328"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="07e47-102">ICorDebugController::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="07e47-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="07e47-103">指定された終了コードを使用してプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="07e47-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07e47-104">このメソッドは、Win32 `TerminateProcess` 関数のラッパーです。</span><span class="sxs-lookup"><span data-stu-id="07e47-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="07e47-105">このため、`Terminate` は、Win32 `TerminateProcess` 関数が使用するのと同じ方法で終了コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="07e47-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e47-106">構文</span><span class="sxs-lookup"><span data-stu-id="07e47-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07e47-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07e47-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="07e47-108">から終了コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="07e47-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="07e47-109">有効な数値は、Winbase. h で定義されています。</span><span class="sxs-lookup"><span data-stu-id="07e47-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07e47-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="07e47-110">Remarks</span></span>  
 <span data-ttu-id="07e47-111">`Terminate` が呼び出されたときにプロセスが停止された場合は、次のようにして、デバッガーがの終了を確認するためのメッセージを次のように使用することで、プロセス[を続行する](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)必要があります:: [ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)または[managedcallback:: exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="07e47-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07e47-112">このメソッドは、アプリケーションドメインによって実装されていません。</span><span class="sxs-lookup"><span data-stu-id="07e47-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="07e47-113">つまり、<xref:System.AppDomain> レベルでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="07e47-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e47-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="07e47-114">Requirements</span></span>  
 <span data-ttu-id="07e47-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e47-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e47-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07e47-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07e47-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07e47-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07e47-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e47-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e47-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="07e47-119">See also</span></span>
