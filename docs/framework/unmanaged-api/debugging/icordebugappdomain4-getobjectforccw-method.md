---
title: ICorDebugAppDomain4::GetObjectForCCW メソッド
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973442a969746671e4d85c5d7881f51c5dfba535
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222264"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="830d6-102">ICorDebugAppDomain4::GetObjectForCCW メソッド</span><span class="sxs-lookup"><span data-stu-id="830d6-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="830d6-103">COM 呼び出し可能ラッパー (CCW: COM Callable Wrapper) ポインターからマネージド オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="830d6-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="830d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="830d6-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="830d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="830d6-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="830d6-106">[in] COM 呼び出し可能ラッパー (CCW) ポインター。</span><span class="sxs-lookup"><span data-stu-id="830d6-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="830d6-107">[out]指定の CCW ポインターに対応するマネージ オブジェクトを表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="830d6-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="830d6-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="830d6-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="830d6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="830d6-109">Requirements</span></span>  
 <span data-ttu-id="830d6-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="830d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="830d6-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="830d6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="830d6-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="830d6-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="830d6-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="830d6-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="830d6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="830d6-114">See also</span></span>

- [<span data-ttu-id="830d6-115">ICorDebugAppDomain4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="830d6-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="830d6-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="830d6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
