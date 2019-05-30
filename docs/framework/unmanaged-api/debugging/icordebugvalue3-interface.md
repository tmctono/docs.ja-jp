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
ms.openlocfilehash: e4bf3605331e6900fd890e49bb3f71f4ca4409c7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377592"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="7f4e2-102">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f4e2-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="7f4e2-103">2 GB を超える配列のサポートを提供する"ICorDebugValue"と"ICorDebugValue2"インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f4e2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7f4e2-104">Methods</span></span>  
  
|<span data-ttu-id="7f4e2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7f4e2-105">Method</span></span>|<span data-ttu-id="7f4e2-106">説明</span><span class="sxs-lookup"><span data-stu-id="7f4e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f4e2-107">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="7f4e2-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="7f4e2-108">これのバイト単位のサイズを取得します。`ICorDebugValue3`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f4e2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f4e2-109">Remarks</span></span>  
 <span data-ttu-id="7f4e2-110">[Icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)メソッドが 0 から 2,147, 483,647 バイトの範囲のオブジェクトのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="7f4e2-111">.NET Framework 4.5 では、配列のサイズは 2 GB を超えることができます。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="7f4e2-112">`ICorDebugValue3`インターフェイスでは、これらの配列のサイズを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f4e2-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7f4e2-113">Requirements</span></span>  
 <span data-ttu-id="7f4e2-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f4e2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f4e2-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f4e2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f4e2-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f4e2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f4e2-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f4e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4e2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f4e2-118">See also</span></span>

- [<span data-ttu-id="7f4e2-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f4e2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7f4e2-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7f4e2-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
