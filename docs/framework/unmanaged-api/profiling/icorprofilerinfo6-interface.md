---
title: ICorProfilerInfo6 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: b1d31012662964132f8b65f030a062ae39ded56e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130363"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="fd439-102">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd439-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="fd439-103">[.NET Framework 4.6 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="fd439-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="fd439-104">特定の NGen モジュールで定義され、特定のメソッドにインラインで定義されているすべてのメソッドの列挙子を提供する[ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="fd439-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd439-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fd439-105">Methods</span></span>  
  
|<span data-ttu-id="fd439-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="fd439-106">Method</span></span>|<span data-ttu-id="fd439-107">説明</span><span class="sxs-lookup"><span data-stu-id="fd439-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd439-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="fd439-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="fd439-109">特定の NGen モジュールに属し、特定のメソッドの本体にインライン化されているすべてのメソッドの列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="fd439-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd439-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="fd439-110">Requirements</span></span>  
 <span data-ttu-id="fd439-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd439-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd439-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd439-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd439-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd439-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd439-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd439-114">See also</span></span>

- [<span data-ttu-id="fd439-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd439-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
