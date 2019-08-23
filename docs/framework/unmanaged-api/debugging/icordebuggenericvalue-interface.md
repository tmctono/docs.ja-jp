---
title: ICorDebugGenericValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36c2ed5529151a7ea18ccaffc2202ad6c69bcbd9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910229"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="d35df-102">ICorDebugGenericValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d35df-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="d35df-103">すべての値に適用される "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="d35df-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="d35df-104">このインターフェイスは、値に対して Get メソッドと Set メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d35df-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d35df-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d35df-105">Methods</span></span>  
  
|<span data-ttu-id="d35df-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d35df-106">Method</span></span>|<span data-ttu-id="d35df-107">説明</span><span class="sxs-lookup"><span data-stu-id="d35df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d35df-108">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="d35df-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="d35df-109">指定したバッファーに値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d35df-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="d35df-110">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="d35df-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="d35df-111">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d35df-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d35df-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d35df-112">Remarks</span></span>  
 <span data-ttu-id="d35df-113">`ICorDebugGenericValue`は、リモート処理が不可能なため、サブインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d35df-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="d35df-114">参照型の場合、値は参照の内容ではなく参照です。</span><span class="sxs-lookup"><span data-stu-id="d35df-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="d35df-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d35df-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d35df-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d35df-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d35df-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="d35df-117">Requirements</span></span>  
 <span data-ttu-id="d35df-118">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d35df-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d35df-119">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d35df-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d35df-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d35df-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d35df-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d35df-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35df-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d35df-122">See also</span></span>

- [<span data-ttu-id="d35df-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d35df-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
