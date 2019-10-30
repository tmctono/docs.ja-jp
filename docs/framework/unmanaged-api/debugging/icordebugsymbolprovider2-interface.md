---
title: ICorDebugSymbolProvider2 インターフェイス
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: fbf6e8ecaf877ac1948b2abbed58526e7a1eec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133563"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="0d6fc-102">ICorDebugSymbolProvider2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d6fc-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="0d6fc-103">追加のデバッグシンボル情報を取得するために、この[プロバイダー](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d6fc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d6fc-104">Methods</span></span>  
  
|<span data-ttu-id="0d6fc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d6fc-105">Method</span></span>|<span data-ttu-id="0d6fc-106">説明</span><span class="sxs-lookup"><span data-stu-id="0d6fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d6fc-107">GetFrameProps メソッド</span><span class="sxs-lookup"><span data-stu-id="0d6fc-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="0d6fc-108">メソッドのメソッド開始位置を示す相対仮想アドレスと、指定されたコード相対仮想アドレスを持つ親フレームを返します。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="0d6fc-109">GetGenericDictionaryInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="0d6fc-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="0d6fc-110">汎用のディクショナリ マップを取得します。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d6fc-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d6fc-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d6fc-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0d6fc-113">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d6fc-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="0d6fc-114">Requirements</span></span>  
 <span data-ttu-id="0d6fc-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d6fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6fc-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d6fc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d6fc-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d6fc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d6fc-118">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d6fc-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6fc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d6fc-119">See also</span></span>

- [<span data-ttu-id="0d6fc-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d6fc-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0d6fc-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d6fc-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0d6fc-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0d6fc-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
