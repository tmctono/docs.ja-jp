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
ms.openlocfilehash: fa22c17ed7d5bcd689f21d2d855d9be7a6a8e164
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892805"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="1fbda-102">ICorDebugComObjectValue::GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="1fbda-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="1fbda-103">現在のランタイム呼び出し可能ラッパー (RCW) にキャッシュされている生のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fbda-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbda-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fbda-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fbda-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fbda-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="1fbda-106">からメソッドが、ランタイム呼び出し可能ラッパー (RCW) によって`IInspectable`キャッシュされた Windows ランタイムインターフェイス (インターフェイス) またはすべての COM インターフェイスだけを返すかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="1fbda-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="1fbda-107">からアドレスを取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="1fbda-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1fbda-108">入出力で実際に`ptrs`返される値`CORDB_ADDRESS`の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1fbda-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="1fbda-109">キャッシュされたインターフェイスオブジェクトのアドレスを格納`CORDB_ADDRESS`している値の配列の開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1fbda-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fbda-110">解説</span><span class="sxs-lookup"><span data-stu-id="1fbda-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fbda-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1fbda-111">Requirements</span></span>  
 <span data-ttu-id="1fbda-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fbda-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fbda-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fbda-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fbda-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fbda-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fbda-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fbda-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbda-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fbda-116">See also</span></span>

- [<span data-ttu-id="1fbda-117">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fbda-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="1fbda-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fbda-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
