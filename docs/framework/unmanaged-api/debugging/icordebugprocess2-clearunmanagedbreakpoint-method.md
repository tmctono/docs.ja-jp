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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4dcfb977f5ca87f2219fd3ed8ef87d16c2defd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948968"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="de2c7-102">ICorDebugProcess2::ClearUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="de2c7-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="de2c7-103">削除前に設定されて、指定されたアドレス ブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="de2c7-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="de2c7-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de2c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de2c7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="de2c7-106">[in]A`CORDB_ADDRESS`ブレークポイントが設定されたアドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="de2c7-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de2c7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="de2c7-107">Remarks</span></span>  
 <span data-ttu-id="de2c7-108">指定したブレークポイントは設定済みに以前の呼び出しによって[icordebugprocess 2::setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="de2c7-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="de2c7-109">`ClearUnmanagedBreakpoint`デバッグ中のプロセスの実行中に、メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="de2c7-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="de2c7-110">`ClearUnmanagedBreakpoint`マネージドのみのモードでデバッガーがアタッチされている場合、または指定したアドレスにブレークポイントが存在しない場合に、エラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="de2c7-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2c7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="de2c7-111">Requirements</span></span>  
 <span data-ttu-id="de2c7-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de2c7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2c7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de2c7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de2c7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2c7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2c7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
