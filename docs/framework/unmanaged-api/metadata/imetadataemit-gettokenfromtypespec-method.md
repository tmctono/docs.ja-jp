---
title: IMetaDataEmit::GetTokenFromTypeSpec メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09256deafdb42847f369664ec8c4bc96d72424d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177607"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="83b2d-102">IMetaDataEmit::GetTokenFromTypeSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="83b2d-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="83b2d-103">指定したメタデータ シグネチャを持つ型のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="83b2d-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b2d-104">構文</span><span class="sxs-lookup"><span data-stu-id="83b2d-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b2d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83b2d-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="83b2d-106">[in]定義されている署名します。</span><span class="sxs-lookup"><span data-stu-id="83b2d-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="83b2d-107">[in]内のバイト数`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="83b2d-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="83b2d-108">[out]`mdTypeSpec`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="83b2d-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b2d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="83b2d-109">Requirements</span></span>  
 <span data-ttu-id="83b2d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b2d-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="83b2d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83b2d-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="83b2d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83b2d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b2d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="83b2d-114">See also</span></span>

- [<span data-ttu-id="83b2d-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83b2d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="83b2d-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83b2d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
