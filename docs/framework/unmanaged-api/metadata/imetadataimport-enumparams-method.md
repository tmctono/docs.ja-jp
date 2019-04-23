---
title: IMetaDataImport::EnumParams メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed5ddd74e61e63426871f659aa1c962d38fd534
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221402"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="5903a-102">IMetaDataImport::EnumParams メソッド</span><span class="sxs-lookup"><span data-stu-id="5903a-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="5903a-103">指定した MethodDef トークンによって参照されるメソッドのパラメーターを表す ParamDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5903a-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5903a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5903a-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5903a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5903a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5903a-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5903a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5903a-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="5903a-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="5903a-108">[in]列挙するためにパラメーターを使用してメソッドを表す MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="5903a-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="5903a-109">[out]ParamDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="5903a-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5903a-110">[in] `rParams` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="5903a-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5903a-111">[out]返される ParamDef トークン数`rParams`します。</span><span class="sxs-lookup"><span data-stu-id="5903a-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5903a-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5903a-112">Return Value</span></span>  
  
|<span data-ttu-id="5903a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5903a-113">HRESULT</span></span>|<span data-ttu-id="5903a-114">説明</span><span class="sxs-lookup"><span data-stu-id="5903a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5903a-115">`EnumParams` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="5903a-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5903a-116">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="5903a-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="5903a-117">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="5903a-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5903a-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="5903a-118">Requirements</span></span>  
 <span data-ttu-id="5903a-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5903a-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5903a-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5903a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5903a-121">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="5903a-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5903a-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5903a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5903a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5903a-123">See also</span></span>

- [<span data-ttu-id="5903a-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5903a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5903a-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5903a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
