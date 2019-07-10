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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afc2192fe46ed75ed6fb75e0d58268152856b746
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770781"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="9ed01-102">IMetaDataEmit::GetTokenFromSig メソッド</span><span class="sxs-lookup"><span data-stu-id="9ed01-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="9ed01-103">指定されたメタデータ署名のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9ed01-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed01-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ed01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ed01-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ed01-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="9ed01-106">[in]永続化して、格納されている署名。</span><span class="sxs-lookup"><span data-stu-id="9ed01-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9ed01-107">[in]内のバイト数`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="9ed01-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="9ed01-108">[out]`mdSignature`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="9ed01-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed01-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ed01-109">Requirements</span></span>  
 <span data-ttu-id="9ed01-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ed01-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed01-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ed01-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ed01-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9ed01-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ed01-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed01-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed01-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ed01-114">See also</span></span>

- [<span data-ttu-id="9ed01-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ed01-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9ed01-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ed01-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
