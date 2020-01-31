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
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794468"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="2a4f5-102">ICorDebugGenericValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a4f5-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="2a4f5-103">すべての値に適用される "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="2a4f5-104">このインターフェイスは、値に対して Get メソッドと Set メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a4f5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a4f5-105">Methods</span></span>  
  
|<span data-ttu-id="2a4f5-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a4f5-106">Method</span></span>|<span data-ttu-id="2a4f5-107">説明</span><span class="sxs-lookup"><span data-stu-id="2a4f5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a4f5-108">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="2a4f5-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="2a4f5-109">指定したバッファーに値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="2a4f5-110">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="2a4f5-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="2a4f5-111">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a4f5-112">コメント</span><span class="sxs-lookup"><span data-stu-id="2a4f5-112">Remarks</span></span>  
 <span data-ttu-id="2a4f5-113">`ICorDebugGenericValue` は、リモート処理が不可能なため、サブインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="2a4f5-114">参照型の場合、値は参照の内容ではなく参照です。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="2a4f5-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a4f5-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a4f5-117">要件</span><span class="sxs-lookup"><span data-stu-id="2a4f5-117">Requirements</span></span>  
 <span data-ttu-id="2a4f5-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a4f5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a4f5-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a4f5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a4f5-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a4f5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a4f5-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a4f5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4f5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4f5-122">See also</span></span>

- [<span data-ttu-id="2a4f5-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a4f5-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
