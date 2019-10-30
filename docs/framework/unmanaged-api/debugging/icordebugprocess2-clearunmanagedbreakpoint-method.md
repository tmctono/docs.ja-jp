---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137244"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="0bacb-102">ICorDebugProcess2::ClearUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="0bacb-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="0bacb-103">指定したアドレスに、以前に設定したブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="0bacb-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bacb-104">構文</span><span class="sxs-lookup"><span data-stu-id="0bacb-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bacb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0bacb-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="0bacb-106">からブレークポイントが設定されたアドレスを示す `CORDB_ADDRESS` 値です。</span><span class="sxs-lookup"><span data-stu-id="0bacb-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bacb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0bacb-107">Remarks</span></span>  
 <span data-ttu-id="0bacb-108">指定されたブレークポイントは、以前の[ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)の呼び出しによって以前に設定されていた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bacb-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="0bacb-109">`ClearUnmanagedBreakpoint` メソッドは、デバッグ中のプロセスの実行中に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0bacb-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="0bacb-110">デバッガーがマネージ専用モードでアタッチされている場合、または指定されたアドレスにブレークポイントが存在しない場合、`ClearUnmanagedBreakpoint` メソッドはエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="0bacb-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bacb-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="0bacb-111">Requirements</span></span>  
 <span data-ttu-id="0bacb-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bacb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bacb-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bacb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bacb-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bacb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bacb-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bacb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
