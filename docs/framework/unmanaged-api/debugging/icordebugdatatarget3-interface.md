---
title: ICorDebugDataTarget3 インターフェイス
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783486"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="0d5b4-102">ICorDebugDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d5b4-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="0d5b4-103">提供され[たモジュール](icordebugdatatarget-interface.md)に関する情報を提供するために、によって、参照インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="0d5b4-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="0d5b4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d5b4-104">Method</span></span>  
  
|<span data-ttu-id="0d5b4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d5b4-105">Method</span></span>|<span data-ttu-id="0d5b4-106">説明</span><span class="sxs-lookup"><span data-stu-id="0d5b4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d5b4-107">GetLoadedModules メソッド</span><span class="sxs-lookup"><span data-stu-id="0d5b4-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="0d5b4-108">これまでに読み込まれたモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d5b4-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d5b4-109">コメント</span><span class="sxs-lookup"><span data-stu-id="0d5b4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d5b4-110">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="0d5b4-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0d5b4-111">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="0d5b4-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5b4-112">要件</span><span class="sxs-lookup"><span data-stu-id="0d5b4-112">Requirements</span></span>  
 <span data-ttu-id="0d5b4-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d5b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5b4-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d5b4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d5b4-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d5b4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d5b4-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5b4-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5b4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d5b4-117">See also</span></span>

- [<span data-ttu-id="0d5b4-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d5b4-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0d5b4-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0d5b4-119">Debugging</span></span>](index.md)
