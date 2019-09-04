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
ms.openlocfilehash: 45a40d49cea2dd5f881fbd47cc2fb4bd96e8f9ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243983"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="3e5cd-102">ICorProfilerInfo8:: GetDynamicFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="3e5cd-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="3e5cd-103">動的メソッドに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e5cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e5cd-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a><span data-ttu-id="3e5cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e5cd-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="3e5cd-106">から情報を取得する対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-106">[in] The ID of the function for which to retrieve information.</span></span>

`moduleId` \
<span data-ttu-id="3e5cd-107">から関数の親クラスが定義されているモジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-107">[in] A pointer to the module in which the function's parent class is defined.</span></span>

`ppvSig` \
<span data-ttu-id="3e5cd-108">入出力関数の署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-108">[out] A pointer to the signature for the function.</span></span>

`pbSig` \
<span data-ttu-id="3e5cd-109">入出力関数シグネチャのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-109">[out] A pointer to the count of bytes for the function signature.</span></span>

`cchName` \
<span data-ttu-id="3e5cd-110">[in] `wszName` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-110">[in] The maximum size of the `wszName` array.</span></span>

`pcchName` \
<span data-ttu-id="3e5cd-111">入出力`wszName`配列内の文字数。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-111">[out] The number of characters in the `wszName` array.</span></span>

`wszName` \
<span data-ttu-id="3e5cd-112">入出力関数の名前`WCHAR` (存在する場合) の配列。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-112">[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e5cd-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e5cd-113">Remarks</span></span>

<span data-ttu-id="3e5cd-114">IL スタブや LCG などの特定のメソッドには、 [IMetaDataImport](../metadata/imetadataimport-interface.md) Api と[IMetaDataImport2](../metadata/imetadataimport2-interface.md) api を使用して取得できるメタデータが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="3e5cd-115">このようなメソッドは、命令ポインターを通じて、または[ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)をリッスンすることによって、プロファイラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="3e5cd-116">この API を使用して、表示名などの動的メソッドに関する情報を取得できます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e5cd-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e5cd-117">Requirements</span></span>

<span data-ttu-id="3e5cd-118">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5cd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3e5cd-119">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="3e5cd-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3e5cd-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="3e5cd-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3e5cd-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5cd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3e5cd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e5cd-122">See also</span></span>

- [<span data-ttu-id="3e5cd-123">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e5cd-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
