---
title: ICorProfilerInfo8 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2cca915eda44d73aea7469e5f752c57309c2300d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495165"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="74039-102">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74039-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="74039-103">動的メソッドに関する情報を照会するメソッドを提供する[ICorProfilerInfo7](icorprofilerinfo7-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="74039-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="74039-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="74039-104">Methods</span></span>  

| <span data-ttu-id="74039-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="74039-105">Method</span></span>|<span data-ttu-id="74039-106">説明</span><span class="sxs-lookup"><span data-stu-id="74039-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="74039-107">IsFunctionDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="74039-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="74039-108">関数にメタデータが関連付けられていないかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="74039-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="74039-109">GetFunctionFromIP3 メソッド</span><span class="sxs-lookup"><span data-stu-id="74039-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="74039-110">マネージコード命令ポインターを FunctionID にマップします。</span><span class="sxs-lookup"><span data-stu-id="74039-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="74039-111">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="74039-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="74039-112">GetDynamicFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="74039-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="74039-113">動的メソッドに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="74039-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="74039-114">要件</span><span class="sxs-lookup"><span data-stu-id="74039-114">Requirements</span></span>  
<span data-ttu-id="74039-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74039-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="74039-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74039-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="74039-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74039-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="74039-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="74039-118">See also</span></span>

- [<span data-ttu-id="74039-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="74039-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
