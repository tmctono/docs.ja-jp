---
title: ICorDebugObjectValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987819"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="7707d-102">ICorDebugObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7707d-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="7707d-103">オブジェクトを含む値を表す"ICorDebugValue"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="7707d-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7707d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-104">Methods</span></span>  
  
|<span data-ttu-id="7707d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-105">Method</span></span>|<span data-ttu-id="7707d-106">説明</span><span class="sxs-lookup"><span data-stu-id="7707d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7707d-107">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="7707d-108">共通言語ランタイム (CLR) へのインターフェイス ポインターを取得<xref:System.Type>オブジェクトのこの`ICorDebugObjectValue`参照。</span><span class="sxs-lookup"><span data-stu-id="7707d-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="7707d-109">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="7707d-110">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="7707d-110">Not implemented.</span></span>|  
|[<span data-ttu-id="7707d-111">GetFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="7707d-112">インターフェイス ポインターを取得、 [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)指定したクラスの指定したフィールドの値を表します。</span><span class="sxs-lookup"><span data-stu-id="7707d-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="7707d-113">GetManagedCopy メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="7707d-114">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="7707d-114">Obsolete.</span></span> <span data-ttu-id="7707d-115">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="7707d-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="7707d-116">GetVirtualMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="7707d-117">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="7707d-117">Not implemented.</span></span>|  
|[<span data-ttu-id="7707d-118">IsValueClass メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="7707d-119">これによって、オブジェクトが参照されるかどうかを示す値を取得します`ICorDebugObjectValue`は値型です。</span><span class="sxs-lookup"><span data-stu-id="7707d-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="7707d-120">SetFromManagedCopy メソッド</span><span class="sxs-lookup"><span data-stu-id="7707d-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="7707d-121">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="7707d-121">Obsolete.</span></span> <span data-ttu-id="7707d-122">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="7707d-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7707d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="7707d-123">Remarks</span></span>  
 <span data-ttu-id="7707d-124">`ICorDebugObjectValue`デバッグ中の処理を続行するまで有効なままになります。</span><span class="sxs-lookup"><span data-stu-id="7707d-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7707d-125">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7707d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7707d-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="7707d-126">Requirements</span></span>  
 <span data-ttu-id="7707d-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7707d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7707d-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7707d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7707d-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7707d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7707d-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7707d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7707d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7707d-131">See also</span></span>

- [<span data-ttu-id="7707d-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7707d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
