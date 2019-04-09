---
title: ICorDebugDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550cb6379ef0d5d17a3446b3f21120208b5a3dad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110189"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="1f5b4-102">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f5b4-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="1f5b4-103">すべての `ICorDebug` デバッグ イベントを派生させる基本インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f5b4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1f5b4-104">Methods</span></span>  
  
|<span data-ttu-id="1f5b4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1f5b4-105">Method</span></span>|<span data-ttu-id="1f5b4-106">説明</span><span class="sxs-lookup"><span data-stu-id="1f5b4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f5b4-107">GetEventKind メソッド</span><span class="sxs-lookup"><span data-stu-id="1f5b4-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="1f5b4-108">この `ICorDebugDebugEvent` オブジェクトが表すイベントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="1f5b4-109">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="1f5b4-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="1f5b4-110">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f5b4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f5b4-111">Remarks</span></span>  
 <span data-ttu-id="1f5b4-112">次のインターフェイスは、`ICorDebugDebugEvent` インターフェイスから派生したものです。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="1f5b4-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="1f5b4-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="1f5b4-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="1f5b4-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="1f5b4-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="1f5b4-116">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f5b4-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f5b4-117">Requirements</span></span>  
 <span data-ttu-id="1f5b4-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f5b4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f5b4-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f5b4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f5b4-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f5b4-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1f5b4-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1f5b4-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f5b4-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f5b4-122">See also</span></span>

- [<span data-ttu-id="1f5b4-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f5b4-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1f5b4-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1f5b4-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
