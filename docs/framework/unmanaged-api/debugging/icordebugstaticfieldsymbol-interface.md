---
title: ICorDebugStaticFieldSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103897"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="8c174-102">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c174-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="8c174-103">静的フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="8c174-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c174-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c174-104">Methods</span></span>  
  
|<span data-ttu-id="8c174-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c174-105">Method</span></span>|<span data-ttu-id="8c174-106">説明</span><span class="sxs-lookup"><span data-stu-id="8c174-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c174-107">GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="8c174-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="8c174-108">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c174-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="8c174-109">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="8c174-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="8c174-110">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c174-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="8c174-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="8c174-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="8c174-112">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c174-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c174-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c174-113">Remarks</span></span>  
 <span data-ttu-id="8c174-114">`ICorDebugStaticFieldSymbol` インターフェイスは、静的フィールドのデバッグ シンボル情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c174-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c174-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="8c174-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8c174-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="8c174-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c174-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c174-117">Requirements</span></span>  
 <span data-ttu-id="8c174-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c174-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c174-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c174-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c174-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c174-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c174-121">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c174-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c174-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c174-122">See also</span></span>

- [<span data-ttu-id="8c174-123">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c174-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="8c174-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c174-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8c174-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8c174-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
