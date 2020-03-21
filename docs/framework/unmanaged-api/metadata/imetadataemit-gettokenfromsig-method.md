---
title: IMetaDataEmit::GetTokenFromSig メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: d02943f28435fc00aad8e319aa260a24cca5e307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177586"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="39a12-102">IMetaDataEmit::GetTokenFromSig メソッド</span><span class="sxs-lookup"><span data-stu-id="39a12-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="39a12-103">指定したメタデータ シグネチャのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a12-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a12-104">構文</span><span class="sxs-lookup"><span data-stu-id="39a12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39a12-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39a12-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="39a12-106">[in]永続化して格納する署名。</span><span class="sxs-lookup"><span data-stu-id="39a12-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="39a12-107">[in]のバイト数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="39a12-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="39a12-108">[アウト]割`mdSignature`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="39a12-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a12-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="39a12-109">Requirements</span></span>  
 <span data-ttu-id="39a12-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a12-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a12-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="39a12-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39a12-112">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="39a12-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39a12-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a12-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a12-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="39a12-114">See also</span></span>

- [<span data-ttu-id="39a12-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a12-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="39a12-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a12-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
