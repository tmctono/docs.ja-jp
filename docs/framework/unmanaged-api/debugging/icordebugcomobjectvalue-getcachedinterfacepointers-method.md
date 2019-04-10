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
ms.openlocfilehash: da0e62250dbef9be93ccee7020e23c3f83e85592
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223278"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="b1c3c-102">ICorDebugComObjectValue::GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="b1c3c-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="b1c3c-103">現在のランタイム呼び出し可能ラッパー (RCW) でキャッシュされた生のインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c3c-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1c3c-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1c3c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1c3c-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="b1c3c-106">[in]メソッドのみを返すかどうかを示す値[!INCLUDE[wrt](../../../../includes/wrt-md.md)]インターフェイス (`IInspectable`インターフェイス) またはランタイム呼び出し可能ラッパー (RCW) でキャッシュされているすべての COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="b1c3c-107">[in]取得するアドレスを持つオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b1c3c-108">[out]数へのポインター`CORDB_ADDRESS`に実際に返される値`ptrs`します。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="b1c3c-109">配列の開始アドレスへのポインター`CORDB_ADDRESS`のアドレスを格納した値は、インターフェイス オブジェクトをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1c3c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1c3c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c3c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1c3c-111">Requirements</span></span>  
 <span data-ttu-id="b1c3c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1c3c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1c3c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1c3c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1c3c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1c3c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1c3c-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b1c3c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1c3c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1c3c-116">See also</span></span>

- [<span data-ttu-id="b1c3c-117">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1c3c-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="b1c3c-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1c3c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
