---
title: ICorProfilerObjectEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8466de39f2f2769fec332290c187ecba396d7d56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080931"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="34c3a-102">ICorProfilerObjectEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="34c3a-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="34c3a-103">コレクション内で固定オブジェクトの合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="34c3a-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="34c3a-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34c3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34c3a-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="34c3a-106">[out]コレクション内の固定オブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="34c3a-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="34c3a-107">このメソッドは常に、.NET Framework version 3.5 で 0 を返します Service Pack 1 (SP1) およびそれ以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="34c3a-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34c3a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="34c3a-108">Requirements</span></span>  
 <span data-ttu-id="34c3a-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34c3a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c3a-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34c3a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34c3a-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34c3a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34c3a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34c3a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c3a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="34c3a-113">See also</span></span>

- [<span data-ttu-id="34c3a-114">ICorProfilerObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34c3a-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
