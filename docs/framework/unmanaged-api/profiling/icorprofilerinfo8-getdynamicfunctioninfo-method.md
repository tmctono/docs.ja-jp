---
title: 'ICorProfilerInfo8:: GetDynamicFunctionInfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 66a08cf60ae4ca9bb6e373d230d0819ee6f9b28c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790006"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="d3e01-102">ICorProfilerInfo8:: GetDynamicFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d3e01-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="d3e01-103">動的メソッドに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3e01-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3e01-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3e01-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="d3e01-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3e01-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d3e01-106">\[] 情報を取得する関数の ID。</span><span class="sxs-lookup"><span data-stu-id="d3e01-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="d3e01-107">で \[] 関数の親クラスが定義されているモジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3e01-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="d3e01-108">\[out] 関数の署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3e01-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="d3e01-109">\[out] 関数シグネチャのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3e01-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="d3e01-110">\[] `wszName` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d3e01-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="d3e01-111">\[out] `wszName` 配列内の文字数。</span><span class="sxs-lookup"><span data-stu-id="d3e01-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="d3e01-112">\[out] 関数の名前 (存在する場合) を `WCHAR` の配列。</span><span class="sxs-lookup"><span data-stu-id="d3e01-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3e01-113">コメント</span><span class="sxs-lookup"><span data-stu-id="d3e01-113">Remarks</span></span>

<span data-ttu-id="d3e01-114">IL スタブや LCG などの特定のメソッドには、 [IMetaDataImport](../metadata/imetadataimport-interface.md) Api と[IMetaDataImport2](../metadata/imetadataimport2-interface.md) api を使用して取得できるメタデータが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d3e01-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="d3e01-115">このようなメソッドは、命令ポインターを通じて、または[ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)をリッスンすることによって、プロファイラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="d3e01-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="d3e01-116">この API を使用して、表示名などの動的メソッドに関する情報を取得できます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="d3e01-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3e01-117">要件</span><span class="sxs-lookup"><span data-stu-id="d3e01-117">Requirements</span></span>

<span data-ttu-id="d3e01-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3e01-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d3e01-119">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3e01-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d3e01-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3e01-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d3e01-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e01-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d3e01-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3e01-122">See also</span></span>

- [<span data-ttu-id="d3e01-123">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3e01-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
