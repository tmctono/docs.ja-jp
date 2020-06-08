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
ms.openlocfilehash: 54c75156c32e5b40aa933ef6530b2cc33edf7de4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490992"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="a385e-102">IMetaDataImport::GetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a385e-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="a385e-103">指定した <xref:System.Security.PermissionSet?displayProperty=nameWithType> アクセス許可トークンによって表されるに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="a385e-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a385e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a385e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a385e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a385e-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="a385e-106">からメタデータプロパティを取得するアクセス許可セットを表すアクセス許可メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="a385e-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="a385e-107">入出力アクセス許可セットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a385e-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="a385e-108">入出力アクセス許可セットのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a385e-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="a385e-109">入出力のサイズ (バイト単位) `ppvPermission` 。</span><span class="sxs-lookup"><span data-stu-id="a385e-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a385e-110">要件</span><span class="sxs-lookup"><span data-stu-id="a385e-110">Requirements</span></span>  
 <span data-ttu-id="a385e-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a385e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a385e-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a385e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a385e-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a385e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a385e-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a385e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a385e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a385e-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="a385e-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a385e-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a385e-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a385e-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
