---
title: IMetaDataImport::EnumMethods メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6237951b7fab013a32a7e717215cacdbe1125b1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493707"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="9e172-102">IMetaDataImport::EnumMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="9e172-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="9e172-103">指定した型のメソッドを表す MethodDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="9e172-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e172-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e172-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e172-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e172-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9e172-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e172-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9e172-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="9e172-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="9e172-108">[in]列挙するメソッドと型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="9e172-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="9e172-109">[out]MethodDef トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="9e172-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9e172-110">[in]MethodDef の最大サイズ`rMethods`配列。</span><span class="sxs-lookup"><span data-stu-id="9e172-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="9e172-111">[out]返される MethodDef トークン数`rMethods`します。</span><span class="sxs-lookup"><span data-stu-id="9e172-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e172-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e172-112">Return Value</span></span>  
  
|<span data-ttu-id="9e172-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e172-113">HRESULT</span></span>|<span data-ttu-id="9e172-114">説明</span><span class="sxs-lookup"><span data-stu-id="9e172-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9e172-115">`EnumMethods` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9e172-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9e172-116">MethodDef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="9e172-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="9e172-117">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="9e172-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e172-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e172-118">Requirements</span></span>  
 <span data-ttu-id="9e172-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e172-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e172-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9e172-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e172-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9e172-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e172-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e172-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e172-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e172-123">See also</span></span>
- [<span data-ttu-id="9e172-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e172-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9e172-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e172-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
