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
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177306"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="b8136-102">IMetaDataImport::EnumMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="b8136-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="b8136-103">指定した型のメソッドを表す MethodDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b8136-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8136-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8136-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8136-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8136-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b8136-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b8136-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b8136-107">このメソッドの最初の呼び出しでは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8136-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="b8136-108">[in]列挙するメソッドを持つ型を表す TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="b8136-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="b8136-109">[アウト]メソッド定義トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="b8136-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b8136-110">[in]メソッド定義`rMethods`配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="b8136-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b8136-111">[アウト]に返される MethodDef トークン`rMethods`の数。</span><span class="sxs-lookup"><span data-stu-id="b8136-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8136-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b8136-112">Return Value</span></span>  
  
|<span data-ttu-id="b8136-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8136-113">HRESULT</span></span>|<span data-ttu-id="b8136-114">説明</span><span class="sxs-lookup"><span data-stu-id="b8136-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b8136-115">`EnumMethods`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b8136-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b8136-116">列挙する MethodDef トークンはありません。</span><span class="sxs-lookup"><span data-stu-id="b8136-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="b8136-117">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="b8136-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8136-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b8136-118">Requirements</span></span>  
 <span data-ttu-id="b8136-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8136-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8136-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="b8136-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8136-121">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="b8136-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8136-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8136-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8136-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8136-123">See also</span></span>

- [<span data-ttu-id="b8136-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8136-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b8136-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8136-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
