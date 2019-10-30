---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123385"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="68593-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド</span><span class="sxs-lookup"><span data-stu-id="68593-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="68593-103">[.NET Framework 4.6 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="68593-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="68593-104">特定の種類の[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)例外コールバックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="68593-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68593-105">構文</span><span class="sxs-lookup"><span data-stu-id="68593-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68593-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68593-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="68593-107">[入力]</span><span class="sxs-lookup"><span data-stu-id="68593-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68593-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="68593-108">Remarks</span></span>  
 <span data-ttu-id="68593-109">`enableExceptionsOutsideOfJMC` の値が `false` の場合:</span><span class="sxs-lookup"><span data-stu-id="68593-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="68593-110">DEBUG_EXCEPTION_FIRST_CHANCE 例外が発生しても、デバッガーへのコールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="68593-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="68593-111">例外がユーザーコードをエスケープしない場合 (つまり、例外の発生元から例外ハンドラーへのパスには、ジャスト Mycode または JMC としてマークされたメソッドがない場合)、DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 例外によってデバッガーへのコールバックが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="68593-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="68593-112">`enableExceptionsOutsideOfJMC` の既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="68593-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68593-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="68593-113">Requirements</span></span>  
 <span data-ttu-id="68593-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68593-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68593-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68593-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68593-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68593-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68593-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68593-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68593-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="68593-118">See also</span></span>

- [<span data-ttu-id="68593-119">ICorDebugProcess8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68593-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="68593-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68593-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
