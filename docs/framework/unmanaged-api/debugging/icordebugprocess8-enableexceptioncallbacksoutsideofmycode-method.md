---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: e54dd051f0dbd9c1964d381c2e05189c375fa66d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210138"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="7d1ab-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode メソッド</span><span class="sxs-lookup"><span data-stu-id="7d1ab-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="7d1ab-103">[.NET Framework 4.6 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="7d1ab-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="7d1ab-104">特定の種類の[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)例外コールバックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1ab-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d1ab-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d1ab-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d1ab-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="7d1ab-107">[入力]</span><span class="sxs-lookup"><span data-stu-id="7d1ab-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d1ab-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d1ab-108">Remarks</span></span>  
 <span data-ttu-id="7d1ab-109">`enableExceptionsOutsideOfJMC` の値が `false` の場合:</span><span class="sxs-lookup"><span data-stu-id="7d1ab-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="7d1ab-110">デバッガーへのコールバックでは DEBUG_EXCEPTION_FIRST_CHANCE 例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="7d1ab-111">例外がユーザー コードにエスケープされることがない場合 (つまり、例外の発生から例外ハンドラーへのパスで、JustMyCode または JMC とマークされているメソッドがない場合)、DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="7d1ab-112">`enableExceptionsOutsideOfJMC` の既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1ab-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d1ab-113">Requirements</span></span>  
 <span data-ttu-id="7d1ab-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1ab-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d1ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d1ab-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d1ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d1ab-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1ab-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d1ab-118">See also</span></span>

- [<span data-ttu-id="7d1ab-119">ICorDebugProcess8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d1ab-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="7d1ab-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d1ab-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
