---
title: ICorDebugVirtualUnwinder インターフェイス
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 59ecf3da4b44af7b04dec26fbc3ea182c185d04a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396453"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="6dbd5-102">ICorDebugVirtualUnwinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dbd5-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="6dbd5-103">スタック アンワインドを支援するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dbd5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6dbd5-104">Methods</span></span>  
  
|<span data-ttu-id="6dbd5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6dbd5-105">Method</span></span>|<span data-ttu-id="6dbd5-106">名前</span><span class="sxs-lookup"><span data-stu-id="6dbd5-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="6dbd5-107">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="6dbd5-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="6dbd5-108">このアンワインダーの現在のコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="6dbd5-109">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6dbd5-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="6dbd5-110">呼び出し元のコンテキストに進みます。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dbd5-111">解説</span><span class="sxs-lookup"><span data-stu-id="6dbd5-111">Remarks</span></span>  
 <span data-ttu-id="6dbd5-112">スタック アンワインドを支援するため、`ICorDebugVirtualUnwinder` インターフェイスのメンバーがデバッガーにより実装されます。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6dbd5-113">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6dbd5-114">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbd5-115">要件</span><span class="sxs-lookup"><span data-stu-id="6dbd5-115">Requirements</span></span>  
 <span data-ttu-id="6dbd5-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dbd5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbd5-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dbd5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dbd5-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dbd5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dbd5-119">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbd5-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbd5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dbd5-120">See also</span></span>

- [<span data-ttu-id="6dbd5-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6dbd5-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6dbd5-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6dbd5-122">Debugging</span></span>](index.md)
