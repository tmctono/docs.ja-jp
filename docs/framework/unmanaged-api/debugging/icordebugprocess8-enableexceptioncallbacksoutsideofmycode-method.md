---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792172"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="5cd7d-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド</span><span class="sxs-lookup"><span data-stu-id="5cd7d-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="5cd7d-103">[.NET Framework 4.6 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="5cd7d-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="5cd7d-104">特定の種類の[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)例外コールバックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="5cd7d-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd7d-105">構文</span><span class="sxs-lookup"><span data-stu-id="5cd7d-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd7d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5cd7d-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="5cd7d-107">[in]</span><span class="sxs-lookup"><span data-stu-id="5cd7d-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cd7d-108">コメント</span><span class="sxs-lookup"><span data-stu-id="5cd7d-108">Remarks</span></span>  
 <span data-ttu-id="5cd7d-109">`enableExceptionsOutsideOfJMC` の値が `false` の場合:</span><span class="sxs-lookup"><span data-stu-id="5cd7d-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="5cd7d-110">デバッガーへのコールバックでは DEBUG_EXCEPTION_FIRST_CHANCE 例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="5cd7d-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="5cd7d-111">例外がユーザー コードにエスケープされることがない場合 (つまり、例外の発生から例外ハンドラーへのパスで、JustMyCode または JMC とマークされているメソッドがない場合)、DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="5cd7d-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="5cd7d-112">`enableExceptionsOutsideOfJMC` の既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="5cd7d-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd7d-113">要件</span><span class="sxs-lookup"><span data-stu-id="5cd7d-113">Requirements</span></span>  
 <span data-ttu-id="5cd7d-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cd7d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd7d-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cd7d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cd7d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cd7d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cd7d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd7d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd7d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cd7d-118">See also</span></span>

- [<span data-ttu-id="5cd7d-119">ICorDebugProcess8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5cd7d-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="5cd7d-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5cd7d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
