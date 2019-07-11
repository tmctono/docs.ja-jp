---
title: IMetaDataEmit::DefinePermissionSet メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16675e8bfde74c1f9c30ac9d52f8eeb919d22477
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777538"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="ab64f-102">IMetaDataEmit::DefinePermissionSet メソッド</span><span class="sxs-lookup"><span data-stu-id="ab64f-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="ab64f-103">指定したメタデータ シグネチャを持つ設定アクセス許可の定義を作成し、そのアクセス許可セットの定義にトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab64f-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab64f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab64f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab64f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab64f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ab64f-106">[in]装飾するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ab64f-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="ab64f-107">[in]A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)使用される宣言セキュリティの種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="ab64f-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="ab64f-108">[in]BLOB の権限です。</span><span class="sxs-lookup"><span data-stu-id="ab64f-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="ab64f-109">[in]サイズ (バイト単位) の`pvPermission`します。</span><span class="sxs-lookup"><span data-stu-id="ab64f-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="ab64f-110">[out]返されるアクセス許可のトークンです。</span><span class="sxs-lookup"><span data-stu-id="ab64f-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab64f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab64f-111">Requirements</span></span>  
 <span data-ttu-id="ab64f-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab64f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab64f-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab64f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab64f-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="ab64f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab64f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab64f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab64f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab64f-116">See also</span></span>

- [<span data-ttu-id="ab64f-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab64f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ab64f-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab64f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
