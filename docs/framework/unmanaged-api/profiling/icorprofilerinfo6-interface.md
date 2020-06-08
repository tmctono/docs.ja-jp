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
ms.openlocfilehash: fba57a88cd3af582b4edf0e5bdbf6ac48020c9f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495515"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="1e534-102">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e534-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="1e534-103">[.NET Framework 4.6 以降のバージョンでサポートされています]</span><span class="sxs-lookup"><span data-stu-id="1e534-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="1e534-104">特定の NGen モジュールで定義され、特定のメソッドにインラインで定義されているすべてのメソッドの列挙子を提供する[ICorProfilerInfo5](icorprofilerinfo5-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="1e534-104">A subclass of [ICorProfilerInfo5](icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e534-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e534-105">Methods</span></span>  
  
|<span data-ttu-id="1e534-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e534-106">Method</span></span>|<span data-ttu-id="1e534-107">説明</span><span class="sxs-lookup"><span data-stu-id="1e534-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e534-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="1e534-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="1e534-109">特定の NGen モジュールに属し、特定のメソッドの本体にインライン化されているすべてのメソッドの列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="1e534-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e534-110">要件</span><span class="sxs-lookup"><span data-stu-id="1e534-110">Requirements</span></span>  
 <span data-ttu-id="1e534-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e534-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e534-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e534-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e534-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e534-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e534-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e534-114">See also</span></span>

- [<span data-ttu-id="1e534-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e534-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
