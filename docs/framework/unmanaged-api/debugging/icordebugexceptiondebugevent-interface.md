---
title: ICorDebugExceptionDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: 168ba2945608a5b26432c5a0f583e5d406f6ce9b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782829"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="4db9d-102">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4db9d-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="4db9d-103">は、例外イベントをサポートするために、の[イベント](icordebugdebugevent-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="4db9d-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4db9d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4db9d-104">Methods</span></span>  
  
|<span data-ttu-id="4db9d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4db9d-105">Method</span></span>|<span data-ttu-id="4db9d-106">説明</span><span class="sxs-lookup"><span data-stu-id="4db9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4db9d-107">GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="4db9d-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="4db9d-108">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="4db9d-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="4db9d-109">GetNativeIP メソッド</span><span class="sxs-lookup"><span data-stu-id="4db9d-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="4db9d-110">この例外デバッグ イベントのネイティブ インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="4db9d-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="4db9d-111">GetStackPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="4db9d-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="4db9d-112">この例外デバッグ イベントのスタック ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="4db9d-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4db9d-113">コメント</span><span class="sxs-lookup"><span data-stu-id="4db9d-113">Remarks</span></span>  
 <span data-ttu-id="4db9d-114">`ICorDebugExceptionDebugEvent` インターフェイスは、次のイベントの種類によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="4db9d-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="4db9d-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="4db9d-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="4db9d-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="4db9d-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="4db9d-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="4db9d-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="4db9d-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="4db9d-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="4db9d-119">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="4db9d-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="4db9d-120">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="4db9d-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db9d-121">要件</span><span class="sxs-lookup"><span data-stu-id="4db9d-121">Requirements</span></span>  
 <span data-ttu-id="4db9d-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4db9d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db9d-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4db9d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4db9d-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4db9d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4db9d-125">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db9d-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db9d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4db9d-126">See also</span></span>

- [<span data-ttu-id="4db9d-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4db9d-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4db9d-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4db9d-128">Debugging</span></span>](index.md)
