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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 510c33b8e0e26bead00dcb85a6ceba102a5f267d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043811"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="246a9-102">IMetaDataEmit::SetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="246a9-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="246a9-103">設定または前回の呼び出しで定義されたアクセス許可セットのメタデータ署名の機能を更新[imetadataemit::definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="246a9-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="246a9-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="246a9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="246a9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="246a9-106">[in]装飾にオブジェクトを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="246a9-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="246a9-107">[in]A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)使用される宣言セキュリティの種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="246a9-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="246a9-108">[in]BLOB の権限です。</span><span class="sxs-lookup"><span data-stu-id="246a9-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="246a9-109">[in]サイズ (バイト単位) の`pvPermission`します。</span><span class="sxs-lookup"><span data-stu-id="246a9-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="246a9-110">[out]`mdPermission`更新されたアクセス許可を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="246a9-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="246a9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="246a9-111">Requirements</span></span>  
 <span data-ttu-id="246a9-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="246a9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="246a9-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="246a9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="246a9-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="246a9-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="246a9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="246a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246a9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="246a9-116">See also</span></span>

- [<span data-ttu-id="246a9-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="246a9-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="246a9-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="246a9-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
