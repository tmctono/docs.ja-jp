---
title: ICorDebugExceptionDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522bccb4a424da620063995d02ae15d09ecbf2fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929875"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="065e9-102">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="065e9-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="065e9-103">は、例外イベントをサポートするために、の[イベント](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="065e9-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="065e9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="065e9-104">Methods</span></span>  
  
|<span data-ttu-id="065e9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="065e9-105">Method</span></span>|<span data-ttu-id="065e9-106">説明</span><span class="sxs-lookup"><span data-stu-id="065e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="065e9-107">GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="065e9-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="065e9-108">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="065e9-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="065e9-109">GetNativeIP メソッド</span><span class="sxs-lookup"><span data-stu-id="065e9-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="065e9-110">この例外デバッグ イベントのネイティブ インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="065e9-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="065e9-111">GetStackPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="065e9-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="065e9-112">この例外デバッグ イベントのスタック ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="065e9-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="065e9-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="065e9-113">Remarks</span></span>  
 <span data-ttu-id="065e9-114">`ICorDebugExceptionDebugEvent` インターフェイスは、次のイベントの種類によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="065e9-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="065e9-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="065e9-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="065e9-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="065e9-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="065e9-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="065e9-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="065e9-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="065e9-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="065e9-119">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="065e9-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="065e9-120">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="065e9-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="065e9-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="065e9-121">Requirements</span></span>  
 <span data-ttu-id="065e9-122">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="065e9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="065e9-123">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="065e9-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="065e9-124">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="065e9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="065e9-125">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="065e9-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065e9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="065e9-126">See also</span></span>

- [<span data-ttu-id="065e9-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="065e9-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="065e9-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="065e9-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
