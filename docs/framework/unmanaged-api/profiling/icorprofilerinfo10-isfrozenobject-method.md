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
ms.openlocfilehash: 250021c9eb475d0cbcb1bd14c8515b969fc9d30b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449826"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="4f8a8-102">ICorProfilerInfo10:: IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="4f8a8-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="4f8a8-103">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4f8a8-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f8a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f8a8-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="4f8a8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f8a8-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="4f8a8-106">から調べるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4f8a8-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="4f8a8-107">入出力オブジェクトが読み取り専用セグメント内にあるかどうかを示す `BOOL`。</span><span class="sxs-lookup"><span data-stu-id="4f8a8-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f8a8-108">要件</span><span class="sxs-lookup"><span data-stu-id="4f8a8-108">Requirements</span></span>

<span data-ttu-id="4f8a8-109">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8a8-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="4f8a8-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f8a8-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4f8a8-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f8a8-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4f8a8-112">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8a8-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4f8a8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f8a8-113">See also</span></span>

- [<span data-ttu-id="4f8a8-114">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f8a8-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
