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
ms.openlocfilehash: 1e6ee1f2f497ef30a5390e7afac55c54705248ed
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007807"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="6d4dd-102">IMetaDataEmit::SetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="6d4dd-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="6d4dd-103">[IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md)の前の呼び出しで定義されたアクセス許可セットのメタデータ署名の機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d4dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d4dd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d4dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d4dd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6d4dd-106">から修飾されるオブジェクトを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="6d4dd-107">から使用する宣言セキュリティの種類を指定する[CorDeclSecurity](cordeclsecurity-enumeration.md)値です。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="6d4dd-108">からアクセス許可 BLOB。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="6d4dd-109">からのサイズ (バイト単位) `pvPermission` 。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="6d4dd-110">入出力`mdPermission`更新されたアクセス許可を表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4dd-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d4dd-111">Requirements</span></span>  
 <span data-ttu-id="6d4dd-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d4dd-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6d4dd-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d4dd-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d4dd-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d4dd-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d4dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4dd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d4dd-116">See also</span></span>

- [<span data-ttu-id="6d4dd-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d4dd-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6d4dd-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d4dd-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
