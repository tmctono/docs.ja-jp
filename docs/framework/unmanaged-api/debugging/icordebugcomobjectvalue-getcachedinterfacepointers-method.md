---
title: ICorDebugComObjectValue::GetCachedInterfacePointers メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: c1e2b557a5e5794c50986b1af8ec39faba845cc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125517"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="2b27c-102">ICorDebugComObjectValue::GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="2b27c-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="2b27c-103">現在のランタイム呼び出し可能ラッパー (RCW) にキャッシュされている生のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2b27c-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b27c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b27c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b27c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b27c-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="2b27c-106">からメソッドが Windows ランタイムインターフェイス (`IInspectable` インターフェイス)、またはランタイム呼び出し可能ラッパー (RCW) によってキャッシュされたすべての COM インターフェイスのみを返すかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="2b27c-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="2b27c-107">からアドレスを取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="2b27c-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2b27c-108">入出力`ptrs`で実際に返される `CORDB_ADDRESS` 値の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2b27c-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="2b27c-109">キャッシュされたインターフェイスオブジェクトのアドレスを格納している `CORDB_ADDRESS` 値の配列の開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2b27c-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b27c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b27c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b27c-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="2b27c-111">Requirements</span></span>  
 <span data-ttu-id="2b27c-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b27c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b27c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b27c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b27c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b27c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b27c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b27c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b27c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b27c-116">See also</span></span>

- [<span data-ttu-id="2b27c-117">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b27c-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="2b27c-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b27c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
