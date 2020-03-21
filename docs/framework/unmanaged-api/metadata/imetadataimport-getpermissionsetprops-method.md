---
title: IMetaDataImport::GetPermissionSetProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175344"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="f0d4c-102">IMetaDataImport::GetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="f0d4c-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="f0d4c-103">指定したアクセス許可トークンによって表<xref:System.Security.PermissionSet?displayProperty=nameWithType>されるに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0d4c-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0d4c-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0d4c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0d4c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0d4c-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="f0d4c-106">[in]メタデータ プロパティを取得するアクセス許可セットを表すアクセス許可メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="f0d4c-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="f0d4c-107">[アウト]アクセス許可セットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0d4c-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="f0d4c-108">[アウト]アクセス許可セットのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0d4c-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="f0d4c-109">[アウト]のサイズ (バイト`ppvPermission`単位)</span><span class="sxs-lookup"><span data-stu-id="f0d4c-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d4c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0d4c-110">Requirements</span></span>  
 <span data-ttu-id="f0d4c-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d4c-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="f0d4c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0d4c-113">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="f0d4c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0d4c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d4c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0d4c-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="f0d4c-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0d4c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f0d4c-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0d4c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
