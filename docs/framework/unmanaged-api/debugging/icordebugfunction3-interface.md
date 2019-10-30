---
title: ICorDebugFunction3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: fc50fd7180aaf5c1cff2147268d34921eec39e8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137764"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="5c3e7-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3e7-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="5c3e7-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="5c3e7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5c3e7-104">により、再 Jit 要求からコードへのアクセスを提供するために、の関数インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="5c3e7-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c3e7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3e7-105">Methods</span></span>  
  
|<span data-ttu-id="5c3e7-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3e7-106">Method</span></span>|<span data-ttu-id="5c3e7-107">説明</span><span class="sxs-lookup"><span data-stu-id="5c3e7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c3e7-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="5c3e7-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="5c3e7-109">アクティブな ReJIT 要求から IL を含む、[コード](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c3e7-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c3e7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c3e7-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3e7-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="5c3e7-111">Requirements</span></span>  
 <span data-ttu-id="5c3e7-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c3e7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3e7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c3e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c3e7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c3e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c3e7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3e7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c3e7-116">See also</span></span>

- [<span data-ttu-id="5c3e7-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c3e7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5c3e7-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5c3e7-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5c3e7-119">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="5c3e7-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
