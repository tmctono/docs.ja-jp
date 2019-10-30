---
title: ICorDebugValue3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140208"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="27c56-102">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27c56-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="27c56-103">"ICorDebugValue" インターフェイスと "ICorDebugValue2" インターフェイスを拡張して、2 GB を超える配列のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="27c56-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27c56-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="27c56-104">Methods</span></span>  
  
|<span data-ttu-id="27c56-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="27c56-105">Method</span></span>|<span data-ttu-id="27c56-106">説明</span><span class="sxs-lookup"><span data-stu-id="27c56-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27c56-107">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="27c56-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="27c56-108">この `ICorDebugValue3` オブジェクトのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="27c56-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27c56-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="27c56-109">Remarks</span></span>  
 <span data-ttu-id="27c56-110">[ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)メソッドは、0 ~ 2147483647 バイトの範囲のオブジェクトサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="27c56-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="27c56-111">.NET Framework 4.5 では、配列のサイズが 2 GB を超える場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c56-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="27c56-112">`ICorDebugValue3` インターフェイスを使用すると、これらの配列のサイズを決定できます。</span><span class="sxs-lookup"><span data-stu-id="27c56-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c56-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="27c56-113">Requirements</span></span>  
 <span data-ttu-id="27c56-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27c56-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27c56-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27c56-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27c56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27c56-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27c56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c56-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="27c56-118">See also</span></span>

- [<span data-ttu-id="27c56-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27c56-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="27c56-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="27c56-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
