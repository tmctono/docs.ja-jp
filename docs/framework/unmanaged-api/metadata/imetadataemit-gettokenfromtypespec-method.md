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
ms.openlocfilehash: ff240a80d2910dcb050cc022257c6eba166bbdc5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465934"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="7235b-102">IMetaDataEmit::GetTokenFromTypeSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="7235b-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="7235b-103">指定したメタデータ シグネチャを持つ型のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="7235b-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7235b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7235b-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7235b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7235b-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="7235b-106">[in]定義されている署名します。</span><span class="sxs-lookup"><span data-stu-id="7235b-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="7235b-107">[in]内のバイト数`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="7235b-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="7235b-108">[out]`mdTypeSpec`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="7235b-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7235b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7235b-109">Requirements</span></span>  
 <span data-ttu-id="7235b-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7235b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7235b-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7235b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7235b-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7235b-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7235b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7235b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7235b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7235b-114">See also</span></span>
- [<span data-ttu-id="7235b-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7235b-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7235b-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7235b-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
