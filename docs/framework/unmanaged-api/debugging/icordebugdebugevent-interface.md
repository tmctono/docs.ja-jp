---
title: ICorDebugDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: a66012651d4b307d06a5a3bff675a248cc0ee376
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976357"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="6badd-102">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6badd-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="6badd-103">すべての `ICorDebug` デバッグ イベントを派生させる基本インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="6badd-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6badd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6badd-104">Methods</span></span>  
  
|<span data-ttu-id="6badd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6badd-105">Method</span></span>|<span data-ttu-id="6badd-106">説明</span><span class="sxs-lookup"><span data-stu-id="6badd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6badd-107">GetEventKind メソッド</span><span class="sxs-lookup"><span data-stu-id="6badd-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="6badd-108">この `ICorDebugDebugEvent` オブジェクトが表すイベントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="6badd-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="6badd-109">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="6badd-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="6badd-110">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="6badd-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6badd-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="6badd-111">Remarks</span></span>  
 <span data-ttu-id="6badd-112">次のインターフェイスは、`ICorDebugDebugEvent` インターフェイスから派生したものです。</span><span class="sxs-lookup"><span data-stu-id="6badd-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="6badd-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6badd-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="6badd-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6badd-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="6badd-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="6badd-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="6badd-116">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="6badd-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6badd-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="6badd-117">Requirements</span></span>  
 <span data-ttu-id="6badd-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6badd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6badd-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6badd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6badd-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6badd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6badd-121">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6badd-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6badd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6badd-122">See also</span></span>

- [<span data-ttu-id="6badd-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6badd-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6badd-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6badd-124">Debugging</span></span>](index.md)
