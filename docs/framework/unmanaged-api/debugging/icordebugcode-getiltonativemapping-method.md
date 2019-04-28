---
title: ICorDebugCode::GetILToNativeMapping メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c30623e53b57a78287b26d4a362793cfb32baede
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750217"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="9b218-102">ICorDebugCode::GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="9b218-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="9b218-103">Microsoft intermediate language (MSIL) オフセットからネイティブ オフセットへのマッピングを表す"COR_DEBUG_IL_TO_NATIVE_MAP"インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b218-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b218-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b218-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b218-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b218-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="9b218-106">[in] `map` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="9b218-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="9b218-107">[out]実際に返される要素数へのポインター、`map`配列。</span><span class="sxs-lookup"><span data-stu-id="9b218-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="9b218-108">[out]配列の`COR_DEBUG_IL_TO_NATIVE_MAP`構造体、MSIL のオフセットからネイティブ オフセットへのマッピングを表します。</span><span class="sxs-lookup"><span data-stu-id="9b218-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="9b218-109">返される要素の配列に順序がありません。</span><span class="sxs-lookup"><span data-stu-id="9b218-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b218-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b218-110">Remarks</span></span>  
 <span data-ttu-id="9b218-111">`GetILToNativeMapping`メソッドは、この"ICorDebugCode"インスタンスは、just-in-time (JIT) MSIL コードをコンパイルしたネイティブ コードを表す場合にのみ、意味のある結果を返します。</span><span class="sxs-lookup"><span data-stu-id="9b218-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b218-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b218-112">Requirements</span></span>  
 <span data-ttu-id="9b218-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b218-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b218-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b218-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b218-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b218-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b218-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b218-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b218-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b218-117">See also</span></span>

- [<span data-ttu-id="9b218-118">ICorDebugCode インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b218-118">ICorDebugCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
