---
title: ICorDebugExceptionDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976006"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="2d516-102">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d516-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="2d516-103">は、例外イベントをサポートするために、の[イベント](icordebugdebugevent-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="2d516-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d516-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d516-104">Methods</span></span>  
  
|<span data-ttu-id="2d516-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d516-105">Method</span></span>|<span data-ttu-id="2d516-106">説明</span><span class="sxs-lookup"><span data-stu-id="2d516-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d516-107">GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="2d516-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="2d516-108">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d516-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="2d516-109">GetNativeIP メソッド</span><span class="sxs-lookup"><span data-stu-id="2d516-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="2d516-110">この例外デバッグ イベントのネイティブ インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d516-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="2d516-111">GetStackPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="2d516-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="2d516-112">この例外デバッグ イベントのスタック ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d516-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d516-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d516-113">Remarks</span></span>  
 <span data-ttu-id="2d516-114">`ICorDebugExceptionDebugEvent` インターフェイスは、次のイベントの種類によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="2d516-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="2d516-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2d516-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="2d516-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2d516-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="2d516-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="2d516-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="2d516-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="2d516-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="2d516-119">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="2d516-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="2d516-120">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d516-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d516-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d516-121">Requirements</span></span>  
 <span data-ttu-id="2d516-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d516-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d516-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d516-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d516-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d516-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d516-125">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d516-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d516-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d516-126">See also</span></span>

- [<span data-ttu-id="2d516-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d516-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2d516-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2d516-128">Debugging</span></span>](index.md)
