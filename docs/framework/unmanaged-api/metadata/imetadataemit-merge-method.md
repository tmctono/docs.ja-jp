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
ms.openlocfilehash: 47b59c7393d9d4e9cbdeaa1a2efd9965f969f985
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497796"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="3f6e7-102">IMetaDataEmit::Merge メソッド</span><span class="sxs-lookup"><span data-stu-id="3f6e7-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="3f6e7-103">指定されたインポートされたスコープをマージするスコープの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f6e7-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f6e7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f6e7-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="3f6e7-106">[in]ポインター、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)マージするインポートされたスコープを識別するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="3f6e7-107">[in]ポインター、 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)トークンの再マップを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="3f6e7-108">[in]ポインター、 [IUnknown](/cpp/atl/iunknown)エラーを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f6e7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f6e7-109">Remarks</span></span>  
 <span data-ttu-id="3f6e7-110">呼び出す[imetadataemit::mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)を 1 つのスコープにメタデータの合併をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6e7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f6e7-111">Requirements</span></span>  
 <span data-ttu-id="3f6e7-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f6e7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6e7-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f6e7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f6e7-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3f6e7-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f6e7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6e7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f6e7-116">See also</span></span>
- [<span data-ttu-id="3f6e7-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f6e7-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3f6e7-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f6e7-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
