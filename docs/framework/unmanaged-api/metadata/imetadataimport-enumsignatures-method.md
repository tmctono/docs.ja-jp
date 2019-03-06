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
ms.openlocfilehash: 3de21f4bb91198a5eb77f94789d0389d97123b7a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472487"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="67b9a-102">IMetaDataImport::EnumSignatures メソッド</span><span class="sxs-lookup"><span data-stu-id="67b9a-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="67b9a-103">現在のスコープ内のスタンドアロン シグネチャを表す Signature トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="67b9a-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="67b9a-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67b9a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67b9a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="67b9a-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="67b9a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="67b9a-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="67b9a-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="67b9a-108">[out]署名トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="67b9a-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="67b9a-109">[in] `rSignatures` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="67b9a-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="67b9a-110">[out]署名のトークンで返される数`rSignatures`します。</span><span class="sxs-lookup"><span data-stu-id="67b9a-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67b9a-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="67b9a-111">Return Value</span></span>  
  
|<span data-ttu-id="67b9a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67b9a-112">HRESULT</span></span>|<span data-ttu-id="67b9a-113">説明</span><span class="sxs-lookup"><span data-stu-id="67b9a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="67b9a-114">`EnumSignatures` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="67b9a-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="67b9a-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="67b9a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="67b9a-116">その場合は、`pcSignatures`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="67b9a-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67b9a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="67b9a-117">Remarks</span></span>  
 <span data-ttu-id="67b9a-118">署名トークンがによって作成された、 [imetadataemit::gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="67b9a-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67b9a-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="67b9a-119">Requirements</span></span>  
 <span data-ttu-id="67b9a-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b9a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b9a-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67b9a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67b9a-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="67b9a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67b9a-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67b9a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b9a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="67b9a-124">See also</span></span>
- [<span data-ttu-id="67b9a-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67b9a-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="67b9a-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67b9a-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
