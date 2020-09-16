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
ms.openlocfilehash: 3755260b885768de6b5b2d6342c0ad590a95caff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548671"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="90cdb-102">ICorProfilerInfo10:: IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="90cdb-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="90cdb-103">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="90cdb-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="90cdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="90cdb-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="90cdb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90cdb-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="90cdb-106">\[in) 調べるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90cdb-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="90cdb-107">\[out] `BOOL` オブジェクトが読み取り専用セグメント内にあるかどうかを示すです。</span><span class="sxs-lookup"><span data-stu-id="90cdb-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="90cdb-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="90cdb-108">Requirements</span></span>

<span data-ttu-id="90cdb-109">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90cdb-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="90cdb-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90cdb-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="90cdb-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90cdb-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="90cdb-112">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cdb-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="90cdb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="90cdb-113">See also</span></span>

- [<span data-ttu-id="90cdb-114">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90cdb-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
