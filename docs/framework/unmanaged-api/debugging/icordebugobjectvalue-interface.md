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
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129760"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="e5880-102">ICorDebugObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5880-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="e5880-103">オブジェクトを含む値を表す "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="e5880-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5880-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-104">Methods</span></span>  
  
|<span data-ttu-id="e5880-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-105">Method</span></span>|<span data-ttu-id="e5880-106">説明</span><span class="sxs-lookup"><span data-stu-id="e5880-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5880-107">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="e5880-108">この `ICorDebugObjectValue` が参照するオブジェクトの共通言語ランタイム (CLR) <xref:System.Type> へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5880-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="e5880-109">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="e5880-110">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="e5880-110">Not implemented.</span></span>|  
|[<span data-ttu-id="e5880-111">GetFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="e5880-112">指定したクラスの指定したフィールドの値を表す、 [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5880-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="e5880-113">GetManagedCopy メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="e5880-114">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="e5880-114">Obsolete.</span></span> <span data-ttu-id="e5880-115">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="e5880-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="e5880-116">GetVirtualMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="e5880-117">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="e5880-117">Not implemented.</span></span>|  
|[<span data-ttu-id="e5880-118">IsValueClass メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="e5880-119">この `ICorDebugObjectValue` によって参照されるオブジェクトが値型かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5880-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="e5880-120">SetFromManagedCopy メソッド</span><span class="sxs-lookup"><span data-stu-id="e5880-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="e5880-121">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="e5880-121">Obsolete.</span></span> <span data-ttu-id="e5880-122">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="e5880-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5880-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5880-123">Remarks</span></span>  
 <span data-ttu-id="e5880-124">`ICorDebugObjectValue` は、デバッグ中のプロセスが続行されるまで有効なままです。</span><span class="sxs-lookup"><span data-stu-id="e5880-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5880-125">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e5880-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5880-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="e5880-126">Requirements</span></span>  
 <span data-ttu-id="e5880-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5880-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5880-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5880-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5880-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5880-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5880-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5880-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5880-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5880-131">See also</span></span>

- [<span data-ttu-id="e5880-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5880-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
