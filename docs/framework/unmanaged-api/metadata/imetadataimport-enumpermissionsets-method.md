---
title: IMetaDataImport::EnumPermissionSets メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175448"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="ace5e-102">IMetaDataImport::EnumPermissionSets メソッド</span><span class="sxs-lookup"><span data-stu-id="ace5e-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="ace5e-103">指定したメタデータ スコープ内のオブジェクトのアクセス許可を列挙します。</span><span class="sxs-lookup"><span data-stu-id="ace5e-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="ace5e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ace5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ace5e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ace5e-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ace5e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ace5e-107">このメソッドの最初の呼び出しでは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace5e-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="ace5e-108">[in]検索の範囲を制限するメタデータ トークン、または可能な限り広い範囲を検索する場合は NULL。</span><span class="sxs-lookup"><span data-stu-id="ace5e-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="ace5e-109">[in]に含`rPermission`める値<xref:System.Security.Permissions.SecurityAction>を表すフラグ、または すべてのアクションを返す 0。</span><span class="sxs-lookup"><span data-stu-id="ace5e-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="ace5e-110">[アウト]アクセス許可トークンの格納に使用される配列。</span><span class="sxs-lookup"><span data-stu-id="ace5e-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ace5e-111">[in] `rPermission` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="ace5e-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ace5e-112">[アウト]で返されるアクセス許可トークンの`rPermission`数。</span><span class="sxs-lookup"><span data-stu-id="ace5e-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ace5e-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ace5e-113">Return Value</span></span>  
  
|<span data-ttu-id="ace5e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ace5e-114">HRESULT</span></span>|<span data-ttu-id="ace5e-115">説明</span><span class="sxs-lookup"><span data-stu-id="ace5e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ace5e-116">`EnumPermissionSets`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ace5e-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ace5e-117">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="ace5e-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="ace5e-118">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="ace5e-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ace5e-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="ace5e-119">Requirements</span></span>  
 <span data-ttu-id="ace5e-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace5e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace5e-121">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="ace5e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ace5e-122">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="ace5e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ace5e-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace5e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace5e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ace5e-124">See also</span></span>

- [<span data-ttu-id="ace5e-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ace5e-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ace5e-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ace5e-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
