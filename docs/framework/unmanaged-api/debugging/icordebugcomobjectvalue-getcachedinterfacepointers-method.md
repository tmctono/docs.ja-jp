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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdbec0101de269b3d5b09e750d552c993a0198ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748479"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="26762-102">ICorDebugComObjectValue::GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="26762-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="26762-103">現在のランタイム呼び出し可能ラッパー (RCW) でキャッシュされた生のインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="26762-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26762-104">構文</span><span class="sxs-lookup"><span data-stu-id="26762-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26762-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26762-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="26762-106">[in]メソッドが唯一の Windows ランタイム インターフェイスを返すかどうかを示す値 (`IInspectable`インターフェイス) またはランタイム呼び出し可能ラッパー (RCW) でキャッシュされているすべての COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="26762-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="26762-107">[in]取得するアドレスを持つオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="26762-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="26762-108">[out]数へのポインター`CORDB_ADDRESS`に実際に返される値`ptrs`します。</span><span class="sxs-lookup"><span data-stu-id="26762-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="26762-109">配列の開始アドレスへのポインター`CORDB_ADDRESS`のアドレスを格納した値は、インターフェイス オブジェクトをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="26762-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26762-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="26762-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26762-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="26762-111">Requirements</span></span>  
 <span data-ttu-id="26762-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26762-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26762-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26762-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26762-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26762-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26762-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26762-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26762-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="26762-116">See also</span></span>

- [<span data-ttu-id="26762-117">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="26762-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="26762-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26762-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
