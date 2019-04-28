---
title: ICorDebugDataTarget2 インターフェイス
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a74ba2b5c1dc2340d20a793bcf3b14e2af234b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789741"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="3d4d7-102">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d4d7-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="3d4d7-103">論理的に拡張し、 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d4d7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-104">Methods</span></span>  
  
|<span data-ttu-id="3d4d7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-105">Method</span></span>|<span data-ttu-id="3d4d7-106">説明</span><span class="sxs-lookup"><span data-stu-id="3d4d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d4d7-107">CreateVirtualUnwinder メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="3d4d7-108">初期コンテキストからアンワインドを開始する新しいスタック アンワインダーを作成します (これは、必ずしもスレッドのリーフではありません)。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="3d4d7-109">EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="3d4d7-110">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="3d4d7-111">GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="3d4d7-112">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="3d4d7-113">GetImageLocation メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="3d4d7-114">モジュールのベース アドレスからモジュールのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="3d4d7-115">GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="3d4d7-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="3d4d7-116">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d4d7-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d4d7-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d4d7-118">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3d4d7-119">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d4d7-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="3d4d7-120">Requirements</span></span>  
 <span data-ttu-id="3d4d7-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d4d7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d4d7-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d4d7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d4d7-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d4d7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d4d7-124">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d4d7-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4d7-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d4d7-125">See also</span></span>

- [<span data-ttu-id="3d4d7-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d4d7-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3d4d7-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3d4d7-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
