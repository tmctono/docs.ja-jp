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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7d9874d4a609c353ae772b75a48af632bf4e85d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756547"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="7a7f3-102">IMetaDataImport::EnumPermissionSets メソッド</span><span class="sxs-lookup"><span data-stu-id="7a7f3-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="7a7f3-103">指定したメタデータ スコープ内のオブジェクトのアクセス許可を列挙します。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a7f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a7f3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7a7f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a7f3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7a7f3-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7a7f3-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="7a7f3-108">[in]できるだけ広い範囲を検索する検索のスコープを制限するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="7a7f3-109">[in]フラグを表す、<xref:System.Security.Permissions.SecurityAction>に含める値`rPermission`、またはすべてのアクションを返す 0。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="7a7f3-110">[out]アクセス許可のトークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7a7f3-111">[in] `rPermission` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7a7f3-112">[out]アクセス許可のトークンで返される数`rPermission`します。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a7f3-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="7a7f3-113">Return Value</span></span>  
  
|<span data-ttu-id="7a7f3-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a7f3-114">HRESULT</span></span>|<span data-ttu-id="7a7f3-115">説明</span><span class="sxs-lookup"><span data-stu-id="7a7f3-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7a7f3-116">`EnumPermissionSets` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7a7f3-117">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="7a7f3-118">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a7f3-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="7a7f3-119">Requirements</span></span>  
 <span data-ttu-id="7a7f3-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a7f3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a7f3-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a7f3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a7f3-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7a7f3-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a7f3-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a7f3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7f3-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a7f3-124">See also</span></span>

- [<span data-ttu-id="7a7f3-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a7f3-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7a7f3-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a7f3-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
