---
title: ICorDebugStaticFieldSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103897"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="75d79-102">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75d79-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="75d79-103">静的フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="75d79-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75d79-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="75d79-104">Methods</span></span>  
  
|<span data-ttu-id="75d79-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="75d79-105">Method</span></span>|<span data-ttu-id="75d79-106">説明</span><span class="sxs-lookup"><span data-stu-id="75d79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75d79-107">GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="75d79-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="75d79-108">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="75d79-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="75d79-109">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="75d79-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="75d79-110">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="75d79-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="75d79-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="75d79-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="75d79-112">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="75d79-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75d79-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="75d79-113">Remarks</span></span>  
 <span data-ttu-id="75d79-114">`ICorDebugStaticFieldSymbol` インターフェイスは、静的フィールドのデバッグ シンボル情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="75d79-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75d79-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="75d79-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="75d79-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="75d79-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d79-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="75d79-117">Requirements</span></span>  
 <span data-ttu-id="75d79-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75d79-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d79-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75d79-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75d79-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75d79-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="75d79-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="75d79-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75d79-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="75d79-122">See also</span></span>

- [<span data-ttu-id="75d79-123">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75d79-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="75d79-124">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="75d79-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="75d79-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="75d79-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
