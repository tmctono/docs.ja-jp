---
title: ICorDebugDataTarget2 インターフェイス
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 472ea0b3d54c025cdd69957765ad2663c7288b15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783574"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="48711-102">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48711-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="48711-103">によって、"の" を論理的に[拡張します](icordebugdatatarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="48711-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48711-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-104">Methods</span></span>  
  
|<span data-ttu-id="48711-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-105">Method</span></span>|<span data-ttu-id="48711-106">説明</span><span class="sxs-lookup"><span data-stu-id="48711-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48711-107">CreateVirtualUnwinder メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="48711-108">初期コンテキストからアンワインドを開始する新しいスタック アンワインダーを作成します (これは、必ずしもスレッドのリーフではありません)。</span><span class="sxs-lookup"><span data-stu-id="48711-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="48711-109">EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="48711-110">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="48711-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="48711-111">GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="48711-112">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="48711-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="48711-113">GetImageLocation メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="48711-114">モジュールのベース アドレスからモジュールのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="48711-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="48711-115">GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="48711-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="48711-116">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="48711-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48711-117">コメント</span><span class="sxs-lookup"><span data-stu-id="48711-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48711-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="48711-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="48711-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="48711-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48711-120">要件</span><span class="sxs-lookup"><span data-stu-id="48711-120">Requirements</span></span>  
 <span data-ttu-id="48711-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48711-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48711-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48711-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48711-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48711-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48711-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48711-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48711-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="48711-125">See also</span></span>

- [<span data-ttu-id="48711-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48711-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="48711-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="48711-127">Debugging</span></span>](index.md)
