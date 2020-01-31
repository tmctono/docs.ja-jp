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
ms.openlocfilehash: 8412020fb98fde245b873a2f0c6a355f6436f712
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868279"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="70373-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses メソッド</span><span class="sxs-lookup"><span data-stu-id="70373-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="70373-103">指定された functionId と rejitId は、現在存在する、このコードのすべての just-in-time バージョンのネイティブコードの開始アドレスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="70373-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="70373-104">構文</span><span class="sxs-lookup"><span data-stu-id="70373-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="70373-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70373-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="70373-106">\[] には、ネイティブコードの開始アドレスを返す関数の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="70373-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="70373-107">\[] JIT 再コンパイルされた関数の id。</span><span class="sxs-lookup"><span data-stu-id="70373-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="70373-108">\[] `codeStartAddresses` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="70373-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="70373-109">\[out] 使用可能なアドレスの数。</span><span class="sxs-lookup"><span data-stu-id="70373-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="70373-110">\[out] `UINT_PTR`の配列。それぞれが指定された関数のネイティブ本体の開始アドレスです。</span><span class="sxs-lookup"><span data-stu-id="70373-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="70373-111">コメント</span><span class="sxs-lookup"><span data-stu-id="70373-111">Remarks</span></span>

<span data-ttu-id="70373-112">階層化コンパイルが有効になっている場合、関数は複数のネイティブコード本体を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="70373-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="70373-113">要件</span><span class="sxs-lookup"><span data-stu-id="70373-113">Requirements</span></span>

<span data-ttu-id="70373-114">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70373-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="70373-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70373-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="70373-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70373-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="70373-117">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70373-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="70373-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="70373-118">See also</span></span>

- [<span data-ttu-id="70373-119">ICorProfilerInfo9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70373-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
