---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ca1643dfa980fa647164accf6432082428124acb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541240"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="00fea-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses メソッド</span><span class="sxs-lookup"><span data-stu-id="00fea-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="00fea-103">指定された functionId と rejitId は、現在存在する、このコードのすべての just-in-time バージョンのネイティブコードの開始アドレスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="00fea-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="00fea-104">構文</span><span class="sxs-lookup"><span data-stu-id="00fea-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="00fea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00fea-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="00fea-106">\[in] ネイティブコードの開始アドレスを返す関数の ID。</span><span class="sxs-lookup"><span data-stu-id="00fea-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="00fea-107">\[in) JIT 再コンパイルされた関数の id。</span><span class="sxs-lookup"><span data-stu-id="00fea-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="00fea-108">\[in] 配列の最大サイズ `codeStartAddresses` 。</span><span class="sxs-lookup"><span data-stu-id="00fea-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="00fea-109">\[out] 使用可能なアドレスの数。</span><span class="sxs-lookup"><span data-stu-id="00fea-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="00fea-110">\[out] の配列 `UINT_PTR` 。各は、指定された関数のネイティブ本体の開始アドレスです。</span><span class="sxs-lookup"><span data-stu-id="00fea-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="00fea-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="00fea-111">Remarks</span></span>

<span data-ttu-id="00fea-112">階層化コンパイルが有効になっている場合、関数は複数のネイティブコード本体を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="00fea-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="00fea-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="00fea-113">Requirements</span></span>

<span data-ttu-id="00fea-114">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00fea-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="00fea-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00fea-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="00fea-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00fea-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="00fea-117">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00fea-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="00fea-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="00fea-118">See also</span></span>

- [<span data-ttu-id="00fea-119">ICorProfilerInfo9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00fea-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
