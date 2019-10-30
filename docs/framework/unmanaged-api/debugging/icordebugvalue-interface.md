---
title: ICorDebugValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140157"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="d1235-102">ICorDebugValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1235-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="d1235-103">デバッグ中のプロセスの値を表します。</span><span class="sxs-lookup"><span data-stu-id="d1235-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="d1235-104">値には、読み取りまたは書き込みの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1235-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1235-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-105">Methods</span></span>  
  
|<span data-ttu-id="d1235-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-106">Method</span></span>|<span data-ttu-id="d1235-107">説明</span><span class="sxs-lookup"><span data-stu-id="d1235-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1235-108">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="d1235-109">このメソッドは現在実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d1235-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="d1235-110">GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="d1235-111">この `ICorDebugValue` オブジェクトのアドレスを取得します。これはデバッグ中のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="d1235-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="d1235-112">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="d1235-113">この `ICorDebugValue` オブジェクトのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1235-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="d1235-114">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="d1235-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="d1235-115">この `ICorDebugValue` オブジェクトのプリミティブ型を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1235-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1235-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1235-116">Remarks</span></span>  
 <span data-ttu-id="d1235-117">一般に、値オブジェクトの所有権は、返されるときに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d1235-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="d1235-118">オブジェクトの終了時に、オブジェクトからの参照を削除するのは、受信者の責任です。</span><span class="sxs-lookup"><span data-stu-id="d1235-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="d1235-119">値が取得された場所によっては、プロセスが再開された後も値が有効なままにならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d1235-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="d1235-120">そのため、一般に、次のように、値は、は、「いいね[:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)メソッドの呼び出し」で保持するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="d1235-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1235-121">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d1235-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1235-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="d1235-122">Requirements</span></span>  
 <span data-ttu-id="d1235-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1235-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1235-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1235-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1235-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1235-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1235-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1235-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1235-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1235-127">See also</span></span>

- [<span data-ttu-id="d1235-128">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1235-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="d1235-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1235-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
