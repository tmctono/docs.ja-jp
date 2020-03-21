---
title: IMetaDataEmit::SetPermissionSetProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177485"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="78b2f-102">IMetaDataEmit::SetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="78b2f-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="78b2f-103">以前の呼び出しで定義されたアクセス許可セットのメタデータ シグネチャ[:Dの](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="78b2f-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78b2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="78b2f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78b2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78b2f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="78b2f-106">[in]装飾されるオブジェクトを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="78b2f-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="78b2f-107">[in]使用する宣言セキュリティの種類を指定する[CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="78b2f-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="78b2f-108">[in]アクセス許可 BLOB。</span><span class="sxs-lookup"><span data-stu-id="78b2f-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="78b2f-109">[in]のサイズ (バイト単位)`pvPermission`です。</span><span class="sxs-lookup"><span data-stu-id="78b2f-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="78b2f-110">[アウト]更新`mdPermission`されたアクセス許可を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="78b2f-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78b2f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="78b2f-111">Requirements</span></span>  
 <span data-ttu-id="78b2f-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b2f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78b2f-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="78b2f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78b2f-114">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="78b2f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78b2f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78b2f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b2f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="78b2f-116">See also</span></span>

- [<span data-ttu-id="78b2f-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78b2f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="78b2f-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78b2f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
