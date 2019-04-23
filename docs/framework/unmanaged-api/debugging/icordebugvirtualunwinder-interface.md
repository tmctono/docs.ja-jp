---
title: ICorDebugVirtualUnwinder インターフェイス
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083401"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="032e9-102">ICorDebugVirtualUnwinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="032e9-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="032e9-103">スタック アンワインドを支援するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="032e9-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="032e9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="032e9-104">Methods</span></span>  
  
|<span data-ttu-id="032e9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="032e9-105">Method</span></span>|<span data-ttu-id="032e9-106">名前</span><span class="sxs-lookup"><span data-stu-id="032e9-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="032e9-107">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="032e9-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="032e9-108">このアンワインダーの現在のコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="032e9-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="032e9-109">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="032e9-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="032e9-110">呼び出し元のコンテキストに進みます。</span><span class="sxs-lookup"><span data-stu-id="032e9-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="032e9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="032e9-111">Remarks</span></span>  
 <span data-ttu-id="032e9-112">スタック アンワインドを支援するため、`ICorDebugVirtualUnwinder` インターフェイスのメンバーがデバッガーにより実装されます。</span><span class="sxs-lookup"><span data-stu-id="032e9-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="032e9-113">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="032e9-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="032e9-114">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="032e9-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="032e9-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="032e9-115">Requirements</span></span>  
 <span data-ttu-id="032e9-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="032e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032e9-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="032e9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="032e9-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="032e9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="032e9-119">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032e9-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032e9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="032e9-120">See also</span></span>

- [<span data-ttu-id="032e9-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="032e9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="032e9-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="032e9-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
