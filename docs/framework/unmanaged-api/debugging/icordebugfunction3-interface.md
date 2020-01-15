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
ms.openlocfilehash: b74008e0a183d46d82c5262209d582537fd155c7
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938084"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="f066e-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f066e-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="f066e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="f066e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f066e-104">ICorDebugFunction インターフェイスを論理的に拡張して、ReJIT 要求からコードへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f066e-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f066e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f066e-105">Methods</span></span>  
  
|<span data-ttu-id="f066e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f066e-106">Method</span></span>|<span data-ttu-id="f066e-107">説明</span><span class="sxs-lookup"><span data-stu-id="f066e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f066e-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="f066e-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="f066e-109">アクティブな ReJIT 要求から IL を含む、[コード](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f066e-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f066e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f066e-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f066e-111">要件</span><span class="sxs-lookup"><span data-stu-id="f066e-111">Requirements</span></span>  
 <span data-ttu-id="f066e-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f066e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f066e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f066e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f066e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f066e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f066e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f066e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f066e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f066e-116">See also</span></span>

- [<span data-ttu-id="f066e-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f066e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f066e-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f066e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="f066e-119">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="f066e-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
