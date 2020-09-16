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
ms.openlocfilehash: 8c9c507f00780d5ef5c5aeb28a1b10493351f37e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546973"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="26b9e-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26b9e-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="26b9e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="26b9e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="26b9e-104">ICorDebugFunction インターフェイスを論理的に拡張して、ReJIT 要求からコードへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="26b9e-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26b9e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="26b9e-105">Methods</span></span>  
  
|<span data-ttu-id="26b9e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="26b9e-106">Method</span></span>|<span data-ttu-id="26b9e-107">説明</span><span class="sxs-lookup"><span data-stu-id="26b9e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26b9e-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="26b9e-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="26b9e-109">アクティブな ReJIT 要求から IL を含む、 [コード](icordebugilcode-interface.md) へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="26b9e-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26b9e-110">解説</span><span class="sxs-lookup"><span data-stu-id="26b9e-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b9e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="26b9e-111">Requirements</span></span>  
 <span data-ttu-id="26b9e-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b9e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b9e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26b9e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26b9e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26b9e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26b9e-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b9e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b9e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="26b9e-116">See also</span></span>

- [<span data-ttu-id="26b9e-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="26b9e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="26b9e-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="26b9e-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="26b9e-119">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="26b9e-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
