---
title: IMetaDataImport::EnumSignatures メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58fa2a6d34f1f3627378c1355a1a292b665899ee
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756412"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="b9f40-102">IMetaDataImport::EnumSignatures メソッド</span><span class="sxs-lookup"><span data-stu-id="b9f40-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="b9f40-103">現在のスコープ内のスタンドアロン シグネチャを表す Signature トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b9f40-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f40-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9f40-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9f40-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b9f40-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9f40-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b9f40-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="b9f40-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="b9f40-108">[out]署名トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="b9f40-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b9f40-109">[in] `rSignatures` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b9f40-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="b9f40-110">[out]署名のトークンで返される数`rSignatures`します。</span><span class="sxs-lookup"><span data-stu-id="b9f40-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9f40-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9f40-111">Return Value</span></span>  
  
|<span data-ttu-id="b9f40-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9f40-112">HRESULT</span></span>|<span data-ttu-id="b9f40-113">説明</span><span class="sxs-lookup"><span data-stu-id="b9f40-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b9f40-114">`EnumSignatures` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="b9f40-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b9f40-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="b9f40-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b9f40-116">その場合は、`pcSignatures`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="b9f40-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9f40-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9f40-117">Remarks</span></span>  
 <span data-ttu-id="b9f40-118">署名トークンがによって作成された、 [imetadataemit::gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="b9f40-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f40-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9f40-119">Requirements</span></span>  
 <span data-ttu-id="b9f40-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9f40-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f40-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9f40-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9f40-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b9f40-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9f40-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f40-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f40-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9f40-124">See also</span></span>

- [<span data-ttu-id="b9f40-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9f40-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b9f40-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9f40-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
