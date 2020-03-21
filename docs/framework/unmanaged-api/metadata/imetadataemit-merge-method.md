---
title: IMetaDataEmit::Merge メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175708"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="59531-102">IMetaDataEmit::Merge メソッド</span><span class="sxs-lookup"><span data-stu-id="59531-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="59531-103">指定されたインポートされたスコープを、マージするスコープのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="59531-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59531-104">構文</span><span class="sxs-lookup"><span data-stu-id="59531-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59531-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59531-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="59531-106">[in]マージするインポートされたスコープを識別する[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59531-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="59531-107">[in]トークンの再マップを指定する[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59531-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="59531-108">[in]エラーを指定する[IUnknown](/cpp/atl/iunknown)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59531-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59531-109">解説</span><span class="sxs-lookup"><span data-stu-id="59531-109">Remarks</span></span>  
 <span data-ttu-id="59531-110">呼び出し[IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)を呼び出して、メタデータの単一のスコープへの結合をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="59531-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59531-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="59531-111">Requirements</span></span>  
 <span data-ttu-id="59531-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59531-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59531-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="59531-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59531-114">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="59531-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59531-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59531-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59531-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="59531-116">See also</span></span>

- [<span data-ttu-id="59531-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59531-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="59531-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59531-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
