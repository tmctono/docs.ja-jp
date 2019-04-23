---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206890"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="4cb20-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="4cb20-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="4cb20-103">メタデータ トークンとトークンに対して指定された関数を使用できるメタデータ インターフェイス インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4cb20-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb20-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cb20-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb20-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cb20-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4cb20-106">[in]メタデータ トークンとメタデータ インターフェイスを取得する対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="4cb20-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="4cb20-107">[in]インスタンスを取得するメタデータ インターフェイスの参照 ID。</span><span class="sxs-lookup"><span data-stu-id="4cb20-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="4cb20-108">[out]指定した関数のトークンに対して使用できるメタデータ インターフェイス インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4cb20-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="4cb20-109">[out]指定された関数のメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4cb20-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb20-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4cb20-110">Requirements</span></span>  
 <span data-ttu-id="4cb20-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb20-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb20-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cb20-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cb20-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb20-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb20-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb20-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cb20-115">See also</span></span>

- [<span data-ttu-id="4cb20-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cb20-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
