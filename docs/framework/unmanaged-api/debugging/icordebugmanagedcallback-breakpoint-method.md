---
title: ICorDebugManagedCallback::Breakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: d8e62499a813419ecc30924624da553ca9f2c7b2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213401"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="820b8-102">ICorDebugManagedCallback::Breakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="820b8-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="820b8-103">ブレークポイントが検出されたときにデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="820b8-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="820b8-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="820b8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="820b8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="820b8-106">からブレークポイントを含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="820b8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="820b8-107">からブレークポイントを含むスレッドを表す、スレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="820b8-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="820b8-108">からブレークポイントを表す ICorDebugBreakpoint オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="820b8-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="820b8-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="820b8-109">Requirements</span></span>  
 <span data-ttu-id="820b8-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="820b8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="820b8-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="820b8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="820b8-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="820b8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="820b8-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="820b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820b8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="820b8-114">See also</span></span>

- [<span data-ttu-id="820b8-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="820b8-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
