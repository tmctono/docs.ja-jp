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
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992304"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="2c1ea-102">IMetaDataImport::EnumSignatures メソッド</span><span class="sxs-lookup"><span data-stu-id="2c1ea-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="2c1ea-103">現在のスコープ内のスタンドアロン シグネチャを表す Signature トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c1ea-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c1ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c1ea-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2c1ea-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2c1ea-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="2c1ea-108">[out]署名トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2c1ea-109">[in] `rSignatures` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="2c1ea-110">[out]署名のトークンで返される数`rSignatures`します。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c1ea-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2c1ea-111">Return Value</span></span>  
  
|<span data-ttu-id="2c1ea-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c1ea-112">HRESULT</span></span>|<span data-ttu-id="2c1ea-113">説明</span><span class="sxs-lookup"><span data-stu-id="2c1ea-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2c1ea-114">`EnumSignatures` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2c1ea-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2c1ea-116">その場合は、`pcSignatures`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1ea-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c1ea-117">Remarks</span></span>  
 <span data-ttu-id="2c1ea-118">署名トークンがによって作成された、 [imetadataemit::gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1ea-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c1ea-119">Requirements</span></span>  
 <span data-ttu-id="2c1ea-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c1ea-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1ea-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c1ea-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c1ea-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2c1ea-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c1ea-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1ea-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1ea-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c1ea-124">See also</span></span>

- [<span data-ttu-id="2c1ea-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c1ea-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2c1ea-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c1ea-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
