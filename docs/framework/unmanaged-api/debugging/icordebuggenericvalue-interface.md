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
ms.openlocfilehash: ad2209c6e28c7749bd149902e5b696955ee7f13f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988677"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="d7635-102">ICorDebugGenericValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7635-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="d7635-103">すべての値に適用される"ICorDebugValue"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="d7635-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="d7635-104">このインターフェイスは、値に対して Get メソッドと Set メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d7635-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7635-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d7635-105">Methods</span></span>  
  
|<span data-ttu-id="d7635-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d7635-106">Method</span></span>|<span data-ttu-id="d7635-107">説明</span><span class="sxs-lookup"><span data-stu-id="d7635-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7635-108">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="d7635-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="d7635-109">指定されたバッファーに値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d7635-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="d7635-110">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="d7635-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="d7635-111">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d7635-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7635-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7635-112">Remarks</span></span>  
 <span data-ttu-id="d7635-113">`ICorDebugGenericValue` 不可能であるサブ インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d7635-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="d7635-114">参照型、値は、参照の内容ではなく、参照です。</span><span class="sxs-lookup"><span data-stu-id="d7635-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="d7635-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d7635-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7635-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d7635-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7635-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7635-117">Requirements</span></span>  
 <span data-ttu-id="d7635-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7635-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7635-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7635-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7635-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7635-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7635-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7635-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7635-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7635-122">See also</span></span>

- [<span data-ttu-id="d7635-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7635-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
