---
title: IMetaDataEmit::SaveToStream メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f6b5582b96dfc83eed482def2c4c4abfeb33a4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207787"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="dea8e-102">IMetaDataEmit::SaveToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="dea8e-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="dea8e-103">指定した現在のスコープ内のすべてのメタデータの保存`IStream`します。</span><span class="sxs-lookup"><span data-stu-id="dea8e-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea8e-104">構文</span><span class="sxs-lookup"><span data-stu-id="dea8e-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dea8e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea8e-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="dea8e-106">[in]保存する書き込み可能なストリーム。</span><span class="sxs-lookup"><span data-stu-id="dea8e-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="dea8e-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="dea8e-107">[in] Reserved.</span></span> <span data-ttu-id="dea8e-108">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="dea8e-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea8e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="dea8e-109">Requirements</span></span>  
 <span data-ttu-id="dea8e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea8e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea8e-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dea8e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dea8e-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="dea8e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dea8e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea8e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea8e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="dea8e-114">See also</span></span>

- [<span data-ttu-id="dea8e-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dea8e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dea8e-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dea8e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
