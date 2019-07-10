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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fee3c0b82bec102d8e292a76d3df5a14d40ace8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757672"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="e44ec-102">IMetaDataEmit::Merge メソッド</span><span class="sxs-lookup"><span data-stu-id="e44ec-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="e44ec-103">指定されたインポートされたスコープをマージするスコープの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="e44ec-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e44ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="e44ec-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e44ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e44ec-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="e44ec-106">[in]ポインター、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)マージするインポートされたスコープを識別するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e44ec-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="e44ec-107">[in]ポインター、 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)トークンの再マップを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e44ec-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="e44ec-108">[in]ポインター、 [IUnknown](/cpp/atl/iunknown)エラーを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e44ec-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e44ec-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e44ec-109">Remarks</span></span>  
 <span data-ttu-id="e44ec-110">呼び出す[imetadataemit::mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)を 1 つのスコープにメタデータの合併をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="e44ec-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e44ec-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e44ec-111">Requirements</span></span>  
 <span data-ttu-id="e44ec-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e44ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e44ec-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e44ec-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e44ec-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="e44ec-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e44ec-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e44ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e44ec-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e44ec-116">See also</span></span>

- [<span data-ttu-id="e44ec-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e44ec-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e44ec-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e44ec-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
