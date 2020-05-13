---
title: ICorDebugMemoryBuffer インターフェイス
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 60f3b0c3230c524ca7d308d3cb80e50b0693715d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212335"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="25e39-102">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25e39-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="25e39-103">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="25e39-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25e39-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="25e39-104">Methods</span></span>  
  
|<span data-ttu-id="25e39-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="25e39-105">Method</span></span>|<span data-ttu-id="25e39-106">説明</span><span class="sxs-lookup"><span data-stu-id="25e39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25e39-107">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="25e39-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="25e39-108">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="25e39-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="25e39-109">GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="25e39-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="25e39-110">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="25e39-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25e39-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="25e39-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25e39-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="25e39-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="25e39-113">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="25e39-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25e39-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="25e39-114">Requirements</span></span>  
 <span data-ttu-id="25e39-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e39-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25e39-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25e39-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25e39-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25e39-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25e39-118">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25e39-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e39-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="25e39-119">See also</span></span>

- [<span data-ttu-id="25e39-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="25e39-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="25e39-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="25e39-121">Debugging</span></span>](index.md)
