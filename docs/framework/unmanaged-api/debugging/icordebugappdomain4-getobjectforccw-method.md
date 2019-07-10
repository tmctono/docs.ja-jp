---
title: ICorDebugAppDomain4::GetObjectForCCW メソッド
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ab4905c55a1395e9ae5cba8343e6b832622005d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737641"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="79276-102">ICorDebugAppDomain4::GetObjectForCCW メソッド</span><span class="sxs-lookup"><span data-stu-id="79276-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="79276-103">COM 呼び出し可能ラッパー (CCW: COM Callable Wrapper) ポインターからマネージド オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="79276-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79276-104">構文</span><span class="sxs-lookup"><span data-stu-id="79276-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79276-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79276-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="79276-106">[in] COM 呼び出し可能ラッパー (CCW) ポインター。</span><span class="sxs-lookup"><span data-stu-id="79276-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="79276-107">[out]指定の CCW ポインターに対応するマネージ オブジェクトを表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="79276-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79276-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="79276-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79276-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="79276-109">Requirements</span></span>  
 <span data-ttu-id="79276-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79276-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79276-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79276-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79276-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79276-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79276-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79276-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79276-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="79276-114">See also</span></span>

- [<span data-ttu-id="79276-115">ICorDebugAppDomain4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79276-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="79276-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79276-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
