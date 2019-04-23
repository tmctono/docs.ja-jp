---
title: IMetaDataEmit::DefineCustomAttribute メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52190583338f1c1ee9183a98d5f4a6cd7236342d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075683"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="6cd55-102">IMetaDataEmit::DefineCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="6cd55-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="6cd55-103">指定したオブジェクトに接続する、指定したメタデータ シグネチャを持つカスタム属性の定義を作成し、そのカスタム属性定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6cd55-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd55-104">構文</span><span class="sxs-lookup"><span data-stu-id="6cd55-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cd55-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6cd55-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6cd55-106">[in]所有者アイテムのトークンです。</span><span class="sxs-lookup"><span data-stu-id="6cd55-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6cd55-107">[in]カスタム属性を識別するトークンです。</span><span class="sxs-lookup"><span data-stu-id="6cd55-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="6cd55-108">[in]カスタム属性へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6cd55-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="6cd55-109">[in]内のバイト数`pCustomAttribute`します。</span><span class="sxs-lookup"><span data-stu-id="6cd55-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="6cd55-110">[out]`mdCustomAttribute`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="6cd55-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd55-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6cd55-111">Requirements</span></span>  
 <span data-ttu-id="6cd55-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cd55-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cd55-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6cd55-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6cd55-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6cd55-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6cd55-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd55-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd55-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cd55-116">See also</span></span>

- [<span data-ttu-id="6cd55-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cd55-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6cd55-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cd55-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
