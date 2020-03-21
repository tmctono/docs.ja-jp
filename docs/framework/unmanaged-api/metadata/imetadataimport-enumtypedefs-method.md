---
title: IMetaDataImport::EnumTypeDefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177298"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="cffaa-102">IMetaDataImport::EnumTypeDefs メソッド</span><span class="sxs-lookup"><span data-stu-id="cffaa-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="cffaa-103">現在のスコープ内のすべての型を表す TypeDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cffaa-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffaa-104">構文</span><span class="sxs-lookup"><span data-stu-id="cffaa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cffaa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cffaa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cffaa-106">[アウト]新しい列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cffaa-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="cffaa-107">このメソッドの最初の呼び出しでは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cffaa-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="cffaa-108">[in]TypeDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="cffaa-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cffaa-109">[in] `rTypeDefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="cffaa-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="cffaa-110">[アウト]に返される TypeDef トークン`rTypeDefs`の数。</span><span class="sxs-lookup"><span data-stu-id="cffaa-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cffaa-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="cffaa-111">Return Value</span></span>  
  
|<span data-ttu-id="cffaa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cffaa-112">HRESULT</span></span>|<span data-ttu-id="cffaa-113">説明</span><span class="sxs-lookup"><span data-stu-id="cffaa-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cffaa-114">`EnumTypeDefs`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="cffaa-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cffaa-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="cffaa-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cffaa-116">その場合は、`pcTypeDefs`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="cffaa-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffaa-117">解説</span><span class="sxs-lookup"><span data-stu-id="cffaa-117">Remarks</span></span>  
 <span data-ttu-id="cffaa-118">TypeDef トークンは、クラスやインターフェイスなどの型、および機能拡張機構を介して追加された型を表します。</span><span class="sxs-lookup"><span data-stu-id="cffaa-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cffaa-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="cffaa-119">Requirements</span></span>  
 <span data-ttu-id="cffaa-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cffaa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cffaa-121">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="cffaa-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cffaa-122">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="cffaa-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cffaa-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cffaa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffaa-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cffaa-124">See also</span></span>

- [<span data-ttu-id="cffaa-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cffaa-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cffaa-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cffaa-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
