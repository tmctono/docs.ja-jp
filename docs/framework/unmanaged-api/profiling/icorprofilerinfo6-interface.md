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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041120"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="6aa1b-102">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aa1b-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="6aa1b-103">[.NET Framework 4.6 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="6aa1b-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="6aa1b-104">サブクラス[ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) NGen モジュールの特定と特定のメソッドをインラインで定義されているすべてのメソッドの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="6aa1b-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6aa1b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6aa1b-105">Methods</span></span>  
  
|<span data-ttu-id="6aa1b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6aa1b-106">Method</span></span>|<span data-ttu-id="6aa1b-107">説明</span><span class="sxs-lookup"><span data-stu-id="6aa1b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6aa1b-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="6aa1b-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="6aa1b-109">指定された NGen モジュールに属していて、特定のメソッドの本体にインライン化ではないすべてのメソッドの列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="6aa1b-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6aa1b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6aa1b-110">Requirements</span></span>  
 <span data-ttu-id="6aa1b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa1b-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6aa1b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6aa1b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa1b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa1b-114">See also</span></span>

- [<span data-ttu-id="6aa1b-115">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aa1b-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
