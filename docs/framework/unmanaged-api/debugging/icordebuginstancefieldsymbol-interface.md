---
title: ICorDebugInstanceFieldSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e5f63df9354df6a4d142c2f6ae12f9a0d5600fb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910138"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="3b534-102">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b534-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="3b534-103">インスタンス フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="3b534-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b534-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b534-104">Methods</span></span>  
  
|<span data-ttu-id="3b534-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b534-105">Method</span></span>|<span data-ttu-id="3b534-106">説明</span><span class="sxs-lookup"><span data-stu-id="3b534-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b534-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="3b534-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="3b534-108">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b534-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="3b534-109">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="3b534-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="3b534-110">このインスタンス フィールドの親クラスにおける、このインスタンス フィールドのオフセット (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b534-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="3b534-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="3b534-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="3b534-112">インスタンス フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b534-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b534-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b534-113">Remarks</span></span>  
 <span data-ttu-id="3b534-114">`ICorDebugInstanceFieldSymbol` インターフェイスは、インスタンス フィールドのデバッグ シンボル情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b534-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b534-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="3b534-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3b534-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="3b534-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b534-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b534-117">Requirements</span></span>  
 <span data-ttu-id="3b534-118">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b534-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b534-119">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3b534-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b534-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="3b534-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b534-121">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b534-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b534-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b534-122">See also</span></span>

- [<span data-ttu-id="3b534-123">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b534-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="3b534-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b534-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3b534-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3b534-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
