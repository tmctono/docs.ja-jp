---
title: ICorDebugMemoryBuffer インターフェイス
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072910"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="e30e6-102">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e30e6-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="e30e6-103">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="e30e6-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e30e6-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e30e6-104">Methods</span></span>  
  
|<span data-ttu-id="e30e6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e30e6-105">Method</span></span>|<span data-ttu-id="e30e6-106">説明</span><span class="sxs-lookup"><span data-stu-id="e30e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e30e6-107">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="e30e6-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="e30e6-108">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e30e6-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="e30e6-109">GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="e30e6-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="e30e6-110">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e30e6-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e30e6-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e30e6-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e30e6-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e30e6-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e30e6-113">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="e30e6-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e30e6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="e30e6-114">Requirements</span></span>  
 <span data-ttu-id="e30e6-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e30e6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e30e6-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e30e6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e30e6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e30e6-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e30e6-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e30e6-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e30e6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e30e6-119">See also</span></span>

- [<span data-ttu-id="e30e6-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e30e6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e30e6-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e30e6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
