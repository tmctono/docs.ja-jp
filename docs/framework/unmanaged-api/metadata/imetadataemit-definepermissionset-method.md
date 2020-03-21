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
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175799"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="b6863-102">IMetaDataEmit::DefinePermissionSet メソッド</span><span class="sxs-lookup"><span data-stu-id="b6863-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="b6863-103">指定したメタデータ シグネチャを持つアクセス許可セットの定義を作成し、そのアクセス許可セット定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6863-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6863-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6863-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6863-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6863-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b6863-106">[in]装飾されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b6863-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="b6863-107">[in]使用する宣言セキュリティの種類を指定する[CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="b6863-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="b6863-108">[in]アクセス許可 BLOB。</span><span class="sxs-lookup"><span data-stu-id="b6863-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="b6863-109">[in]のサイズ (バイト単位)`pvPermission`です。</span><span class="sxs-lookup"><span data-stu-id="b6863-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="b6863-110">[アウト]返されたアクセス許可トークン。</span><span class="sxs-lookup"><span data-stu-id="b6863-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6863-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b6863-111">Requirements</span></span>  
 <span data-ttu-id="b6863-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6863-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6863-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="b6863-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6863-114">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6863-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6863-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6863-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6863-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6863-116">See also</span></span>

- [<span data-ttu-id="b6863-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6863-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b6863-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6863-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
