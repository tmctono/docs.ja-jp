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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993729"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="26464-102">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26464-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="26464-103">2 GB を超える配列のサポートを提供する"ICorDebugValue"と"ICorDebugValue2"インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="26464-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26464-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="26464-104">Methods</span></span>  
  
|<span data-ttu-id="26464-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="26464-105">Method</span></span>|<span data-ttu-id="26464-106">説明</span><span class="sxs-lookup"><span data-stu-id="26464-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26464-107">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="26464-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="26464-108">これのバイト単位のサイズを取得します。`ICorDebugValue3`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="26464-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26464-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="26464-109">Remarks</span></span>  
 <span data-ttu-id="26464-110">[Icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)メソッドが 0 から 2,147, 483,647 バイトの範囲のオブジェクトのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="26464-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="26464-111">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]配列のサイズが 2 GB を超えることができます。</span><span class="sxs-lookup"><span data-stu-id="26464-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="26464-112">`ICorDebugValue3`インターフェイスでは、これらの配列のサイズを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="26464-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26464-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="26464-113">Requirements</span></span>  
 <span data-ttu-id="26464-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26464-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26464-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26464-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26464-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26464-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26464-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26464-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26464-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="26464-118">See also</span></span>

- [<span data-ttu-id="26464-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26464-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="26464-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="26464-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
