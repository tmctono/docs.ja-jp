---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973992"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="1dcbf-102">ICorProfilerInfo10:: IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="1dcbf-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="1dcbf-103">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1dcbf-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="1dcbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="1dcbf-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="1dcbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1dcbf-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="1dcbf-106">から調べるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1dcbf-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="1dcbf-107">入出力オブジェクトが読み取り専用セグメント内にあるかどうかを示すです。`BOOL`</span><span class="sxs-lookup"><span data-stu-id="1dcbf-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="1dcbf-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="1dcbf-108">Requirements</span></span>  
 <span data-ttu-id="1dcbf-109">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcbf-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="1dcbf-110">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="1dcbf-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1dcbf-111">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="1dcbf-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dcbf-112">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dcbf-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1dcbf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dcbf-113">See also</span></span>
- [<span data-ttu-id="1dcbf-114">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1dcbf-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

