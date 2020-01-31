---
title: ICorProfilerInfo8 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868318"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="4596a-102">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4596a-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="4596a-103">動的メソッドに関する情報を照会するメソッドを提供する[ICorProfilerInfo7](icorprofilerinfo7-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="4596a-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="4596a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4596a-104">Methods</span></span>  

| <span data-ttu-id="4596a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4596a-105">Method</span></span>|<span data-ttu-id="4596a-106">説明</span><span class="sxs-lookup"><span data-stu-id="4596a-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="4596a-107">IsFunctionDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="4596a-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="4596a-108">関数にメタデータが関連付けられていないかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4596a-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="4596a-109">GetFunctionFromIP3 メソッド</span><span class="sxs-lookup"><span data-stu-id="4596a-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="4596a-110">マネージコード命令ポインターを FunctionID にマップします。</span><span class="sxs-lookup"><span data-stu-id="4596a-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="4596a-111">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="4596a-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="4596a-112">GetDynamicFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="4596a-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="4596a-113">動的メソッドに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4596a-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4596a-114">要件</span><span class="sxs-lookup"><span data-stu-id="4596a-114">Requirements</span></span>  
<span data-ttu-id="4596a-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4596a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4596a-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4596a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="4596a-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4596a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4596a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4596a-118">See also</span></span>

- [<span data-ttu-id="4596a-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4596a-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
