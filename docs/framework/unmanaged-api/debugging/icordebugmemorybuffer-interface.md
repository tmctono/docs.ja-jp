---
title: ICorDebugMemoryBuffer インターフェイス
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: fa1bbca1e771cbc2b3475891862875b97b9e7f90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793137"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="6a57f-102">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a57f-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="6a57f-103">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="6a57f-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a57f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a57f-104">Methods</span></span>  
  
|<span data-ttu-id="6a57f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a57f-105">Method</span></span>|<span data-ttu-id="6a57f-106">説明</span><span class="sxs-lookup"><span data-stu-id="6a57f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a57f-107">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="6a57f-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="6a57f-108">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a57f-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="6a57f-109">GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="6a57f-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="6a57f-110">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a57f-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a57f-111">コメント</span><span class="sxs-lookup"><span data-stu-id="6a57f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a57f-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="6a57f-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6a57f-113">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="6a57f-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a57f-114">要件</span><span class="sxs-lookup"><span data-stu-id="6a57f-114">Requirements</span></span>  
 <span data-ttu-id="6a57f-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a57f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a57f-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a57f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a57f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a57f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a57f-118">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a57f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a57f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a57f-119">See also</span></span>

- [<span data-ttu-id="6a57f-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a57f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6a57f-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6a57f-121">Debugging</span></span>](index.md)
