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
ms.openlocfilehash: 8c609d730297881c0ac20dca8569f0e9492638e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175721"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="2a437-102">IMetaDataEmit::GetTokenFromTypeSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="2a437-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="2a437-103">指定したメタデータ シグネチャを持つ型のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a437-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a437-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a437-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a437-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a437-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="2a437-106">[in]定義されているシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="2a437-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="2a437-107">[in]のバイト数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="2a437-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="2a437-108">[アウト]割`mdTypeSpec`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="2a437-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a437-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a437-109">Requirements</span></span>  
 <span data-ttu-id="2a437-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a437-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a437-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="2a437-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a437-112">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a437-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a437-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a437-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a437-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a437-114">See also</span></span>

- [<span data-ttu-id="2a437-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a437-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2a437-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a437-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
