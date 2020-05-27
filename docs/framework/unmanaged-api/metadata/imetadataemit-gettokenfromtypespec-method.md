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
ms.openlocfilehash: 1cd09fe785bb37c892417ddbf1efaaaa90e121bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009237"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="f26ae-102">IMetaDataEmit::GetTokenFromTypeSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="f26ae-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="f26ae-103">指定したメタデータシグネチャを持つ型のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f26ae-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f26ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="f26ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f26ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f26ae-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="f26ae-106">から定義されている署名。</span><span class="sxs-lookup"><span data-stu-id="f26ae-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f26ae-107">からのバイト数 `pvSig` 。</span><span class="sxs-lookup"><span data-stu-id="f26ae-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="f26ae-108">入出力`mdTypeSpec`割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="f26ae-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f26ae-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f26ae-109">Requirements</span></span>  
 <span data-ttu-id="f26ae-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26ae-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f26ae-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f26ae-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f26ae-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f26ae-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f26ae-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f26ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f26ae-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f26ae-114">See also</span></span>

- [<span data-ttu-id="f26ae-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f26ae-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f26ae-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f26ae-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
