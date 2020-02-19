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
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452189"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="6bd27-102">ICorProfilerInfo10:: IsFrozenObject メソッド</span><span class="sxs-lookup"><span data-stu-id="6bd27-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="6bd27-103">ObjectID が指定された場合、オブジェクトが読み取り専用セグメント内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6bd27-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="6bd27-104">構文</span><span class="sxs-lookup"><span data-stu-id="6bd27-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="6bd27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bd27-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="6bd27-106">\[] を確認するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6bd27-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="6bd27-107">\[out] オブジェクトが読み取り専用セグメント内にあるかどうかを示す `BOOL`。</span><span class="sxs-lookup"><span data-stu-id="6bd27-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="6bd27-108">要件</span><span class="sxs-lookup"><span data-stu-id="6bd27-108">Requirements</span></span>

<span data-ttu-id="6bd27-109">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bd27-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="6bd27-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6bd27-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6bd27-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bd27-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6bd27-112">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd27-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6bd27-113">参照</span><span class="sxs-lookup"><span data-stu-id="6bd27-113">See also</span></span>

- [<span data-ttu-id="6bd27-114">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6bd27-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
