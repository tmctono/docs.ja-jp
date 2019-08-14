---
title: ICorProfilerInfo8 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973822"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="845df-102">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="845df-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="845df-103">動的メソッドに関する情報を照会するメソッドを提供する[ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="845df-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="845df-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="845df-104">Methods</span></span>  

| <span data-ttu-id="845df-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="845df-105">Method</span></span>|<span data-ttu-id="845df-106">説明</span><span class="sxs-lookup"><span data-stu-id="845df-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="845df-107">IsFunctionDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="845df-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="845df-108">関数にメタデータが関連付けられていないかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="845df-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="845df-109">GetFunctionFromIP3 メソッド</span><span class="sxs-lookup"><span data-stu-id="845df-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="845df-110">マネージコード命令ポインターを FunctionID にマップします。</span><span class="sxs-lookup"><span data-stu-id="845df-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="845df-111">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="845df-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="845df-112">GetDynamicFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="845df-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="845df-113">動的メソッドに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="845df-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="845df-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="845df-114">Requirements</span></span>  
<span data-ttu-id="845df-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="845df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="845df-116">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="845df-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="845df-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="845df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="845df-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="845df-118">See also</span></span>
- [<span data-ttu-id="845df-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="845df-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
