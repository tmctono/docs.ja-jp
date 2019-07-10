---
title: ICorDebugBlockingObjectEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd82418da26ab0cd32b007b4613d588dfa695eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745291"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="36c62-102">ICorDebugBlockingObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="36c62-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="36c62-103">指定した数を取得[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)列挙体の現在位置からのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="36c62-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c62-104">構文</span><span class="sxs-lookup"><span data-stu-id="36c62-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36c62-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="36c62-106">[in]取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="36c62-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="36c62-107">[out]ポインターの配列[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="36c62-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="36c62-108">[out]取得されたオブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="36c62-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36c62-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="36c62-109">Return Value</span></span>  
 <span data-ttu-id="36c62-110">このメソッドは、次の特定の HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="36c62-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="36c62-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36c62-111">HRESULT</span></span>|<span data-ttu-id="36c62-112">説明</span><span class="sxs-lookup"><span data-stu-id="36c62-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36c62-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="36c62-113">S_OK</span></span>|<span data-ttu-id="36c62-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="36c62-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="36c62-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="36c62-115">S_FALSE</span></span>|<span data-ttu-id="36c62-116">`pceltFetched` は `celt` と一致しません。</span><span class="sxs-lookup"><span data-stu-id="36c62-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36c62-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="36c62-117">Remarks</span></span>  
 <span data-ttu-id="36c62-118">このメソッドが機能などの一般的な COM の列挙子。</span><span class="sxs-lookup"><span data-stu-id="36c62-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="36c62-119">入力配列の値は以上である必要がありますサイズの`celt`します。</span><span class="sxs-lookup"><span data-stu-id="36c62-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="36c62-120">配列で塗りつぶされますか、[次へ]`celt`値よりも少ない場合は列挙体で、または残りのすべての値を持つ`celt`ままにします。</span><span class="sxs-lookup"><span data-stu-id="36c62-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="36c62-121">このメソッドが戻るとき`pceltFetched`取得された値の数で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="36c62-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="36c62-122">場合`values`無効なポインターが格納または未満であるバッファーを指す`celt`、または`pceltFetched`無効なポインターが、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="36c62-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36c62-123">ただし、 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体を解放する必要はありません、その内部に"ICorDebugValue"インターフェイスが解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36c62-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c62-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="36c62-124">Requirements</span></span>  
 <span data-ttu-id="36c62-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c62-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c62-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36c62-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36c62-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36c62-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36c62-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c62-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c62-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c62-129">See also</span></span>

- [<span data-ttu-id="36c62-130">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c62-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="36c62-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c62-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="36c62-132">デバッグ</span><span class="sxs-lookup"><span data-stu-id="36c62-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
