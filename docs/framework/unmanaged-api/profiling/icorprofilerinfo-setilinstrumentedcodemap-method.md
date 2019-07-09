---
title: ICorProfilerInfo::SetILInstrumentedCodeMap メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41df91ceb9e4b776c2aa1ce864b7e09ec485fd5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661949"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="6ebae-102">ICorProfilerInfo::SetILInstrumentedCodeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="6ebae-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="6ebae-103">指定された Microsoft intermediate language (MSIL) のマップ エントリを使用して、指定された関数のコード マップを設定します。</span><span class="sxs-lookup"><span data-stu-id="6ebae-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="6ebae-104">呼び出す .NET Framework version 2.0 で`SetILInstrumentedCodeMap`で、`FunctionID`ジェネリック関数の特定のアプリケーション ドメインで表すには、アプリケーション ドメインでは、その関数のすべてのインスタンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="6ebae-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ebae-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ebae-105">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="6ebae-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ebae-106">Parameters</span></span>

`functionId`\
<span data-ttu-id="6ebae-107">[in]コード マップを設定する対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="6ebae-107">[in] The ID of the function for which to set the code map.</span></span>

`fStartJit`\
<span data-ttu-id="6ebae-108">[in]示すブール値かどうかを呼び出し、`SetILInstrumentedCodeMap`メソッドは、特定の 1 つ目`FunctionID`します。</span><span class="sxs-lookup"><span data-stu-id="6ebae-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="6ebae-109">設定`fStartJit`に`true`最初の呼び出しで`SetILInstrumentedCodeMap`の指定された`FunctionID`、および`false`以降。</span><span class="sxs-lookup"><span data-stu-id="6ebae-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

`cILMapEntries`\
<span data-ttu-id="6ebae-110">[in]要素の数、`cILMapEntries`配列。</span><span class="sxs-lookup"><span data-stu-id="6ebae-110">[in] The number of elements in the `cILMapEntries` array.</span></span>

`rgILMapEntries`\
<span data-ttu-id="6ebae-111">[in]COR_IL_MAP 構造体の MSIL オフセットを指定の配列。</span><span class="sxs-lookup"><span data-stu-id="6ebae-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ebae-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ebae-112">Remarks</span></span>

<span data-ttu-id="6ebae-113">プロファイラーは、(たとえば、指定されたソース行に達したときに通知する場合など) には、そのメソッドをインストルメント化するために多くの場合、メソッドのソース コード内のステートメントを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6ebae-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="6ebae-114">`SetILInstrumentedCodeMap` 元の MSIL 命令を新しい場所にマップするプロファイラーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ebae-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="6ebae-115">プロファイラーを使用できる、 [icorprofilerinfo::getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)特定のネイティブ オフセットの元の MSIL オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="6ebae-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="6ebae-116">デバッガーには、古い各オフセットが、変更されていない元の MSIL コード内のオフセット、MSIL を指すことと、新しい各オフセットがインストルメント化された新しいコード内の MSIL オフセットを指すことが前提としています。</span><span class="sxs-lookup"><span data-stu-id="6ebae-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="6ebae-117">マップは、昇順で並べ替え 必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebae-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="6ebae-118">適切に機能するステップの場合これらのガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="6ebae-118">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="6ebae-119">インストルメント化された MSIL コードの順序を変更しません。</span><span class="sxs-lookup"><span data-stu-id="6ebae-119">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="6ebae-120">元の MSIL コードを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ebae-120">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="6ebae-121">マップでは、プログラム データベース (PDB) ファイルからのすべてのシーケンス ポイントのエントリを含めます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="6ebae-122">マップに存在しないエントリが補間されません。</span><span class="sxs-lookup"><span data-stu-id="6ebae-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="6ebae-123">そのため、次のマップを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-123">So, given the following map:</span></span>

  <span data-ttu-id="6ebae-124">(新しい 0、0)</span><span class="sxs-lookup"><span data-stu-id="6ebae-124">(0 old, 0 new)</span></span>

  <span data-ttu-id="6ebae-125">(新しい 5、10)</span><span class="sxs-lookup"><span data-stu-id="6ebae-125">(5 old, 10 new)</span></span>

  <span data-ttu-id="6ebae-126">(新しい 9、20)</span><span class="sxs-lookup"><span data-stu-id="6ebae-126">(9 old, 20 new)</span></span>

  - <span data-ttu-id="6ebae-127">0、1、2、3、または 4 の以前のオフセットは、新しいオフセット 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="6ebae-128">5、6、7、または 8 の以前のオフセットは、10 の新しいオフセットにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="6ebae-129">9 以降の以前のオフセットは、20 の新しいオフセットにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="6ebae-130">0、1、2、3、4、5、6、7、8、または 9 の新しいオフセットは、以前のオフセット 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="6ebae-131">10、11、12、13、14、15、16、17、18 または 19 の新しいオフセットは、以前のオフセット 5 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="6ebae-132">20 以上の新しいオフセットは、以前のオフセット 9 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6ebae-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ebae-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ebae-133">Requirements</span></span>

<span data-ttu-id="6ebae-134">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ebae-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6ebae-135">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ebae-135">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6ebae-136">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ebae-136">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6ebae-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ebae-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6ebae-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ebae-138">See also</span></span>

- [<span data-ttu-id="6ebae-139">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ebae-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
