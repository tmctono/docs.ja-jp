---
title: ICorDebugDataTarget2 インターフェイス
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976435"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="eb5cf-102">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb5cf-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="eb5cf-103">によって、"の" を論理的に[拡張します](icordebugdatatarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb5cf-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-104">Methods</span></span>  
  
|<span data-ttu-id="eb5cf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-105">Method</span></span>|<span data-ttu-id="eb5cf-106">説明</span><span class="sxs-lookup"><span data-stu-id="eb5cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb5cf-107">CreateVirtualUnwinder メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="eb5cf-108">初期コンテキストからアンワインドを開始する新しいスタック アンワインダーを作成します (これは、必ずしもスレッドのリーフではありません)。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="eb5cf-109">EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="eb5cf-110">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="eb5cf-111">GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="eb5cf-112">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="eb5cf-113">GetImageLocation メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="eb5cf-114">モジュールのベース アドレスからモジュールのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="eb5cf-115">GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5cf-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="eb5cf-116">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb5cf-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb5cf-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb5cf-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="eb5cf-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb5cf-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb5cf-120">Requirements</span></span>  
 <span data-ttu-id="eb5cf-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb5cf-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb5cf-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb5cf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb5cf-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb5cf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb5cf-124">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb5cf-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5cf-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb5cf-125">See also</span></span>

- [<span data-ttu-id="eb5cf-126">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb5cf-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="eb5cf-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="eb5cf-127">Debugging</span></span>](index.md)
