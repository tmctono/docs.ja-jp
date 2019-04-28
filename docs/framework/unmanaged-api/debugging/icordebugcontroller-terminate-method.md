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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c8dd8795fc3699176490ea0bb9b2e999038afb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749073"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="0e8ea-102">ICorDebugController::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="0e8ea-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="0e8ea-103">指定した終了コードを使用して、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e8ea-104">このメソッドは、win32 ラッパー`TerminateProcess`関数。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="0e8ea-105">したがって、`Terminate`終了コードを使用して、同じ方法、Win32`TerminateProcess`関数では使用します。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8ea-106">構文</span><span class="sxs-lookup"><span data-stu-id="0e8ea-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e8ea-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e8ea-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="0e8ea-108">[in]終了コードを示す数値。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="0e8ea-109">有効な数値の値は、Winbase.h で定義されます。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e8ea-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e8ea-110">Remarks</span></span>  
 <span data-ttu-id="0e8ea-111">プロセスが停止している場合`Terminate`が呼び出されると、プロセスを続行するかを使用して、 [icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)メソッド、デバッガーを使用して、終了の確認を受信するように、 [Icordebugmanagedcallback::exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)または[icordebugmanagedcallback::exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e8ea-112">このメソッドは、アプリケーション ドメインによって実装されていません。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="0e8ea-113">実装されていない、つまり、<xref:System.AppDomain>レベル。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e8ea-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0e8ea-114">Requirements</span></span>  
 <span data-ttu-id="0e8ea-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e8ea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e8ea-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e8ea-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e8ea-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e8ea-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e8ea-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8ea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8ea-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e8ea-119">See also</span></span>
