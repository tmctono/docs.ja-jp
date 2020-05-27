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
ms.openlocfilehash: a069e2f4ec5d4114e9504fa5a58c5066fdfd7249
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008041"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="72ab0-102">IMetaDataEmit::DefinePermissionSet メソッド</span><span class="sxs-lookup"><span data-stu-id="72ab0-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="72ab0-103">指定したメタデータシグネチャを持つアクセス許可セットの定義を作成し、そのアクセス許可セットの定義に対するトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="72ab0-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ab0-104">構文</span><span class="sxs-lookup"><span data-stu-id="72ab0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72ab0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ab0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="72ab0-106">から修飾されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72ab0-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="72ab0-107">から使用する宣言セキュリティの種類を指定する[CorDeclSecurity](cordeclsecurity-enumeration.md)値です。</span><span class="sxs-lookup"><span data-stu-id="72ab0-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="72ab0-108">からアクセス許可 BLOB。</span><span class="sxs-lookup"><span data-stu-id="72ab0-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="72ab0-109">からのサイズ (バイト単位) `pvPermission` 。</span><span class="sxs-lookup"><span data-stu-id="72ab0-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="72ab0-110">入出力返されたアクセス許可トークン。</span><span class="sxs-lookup"><span data-stu-id="72ab0-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ab0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="72ab0-111">Requirements</span></span>  
 <span data-ttu-id="72ab0-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72ab0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ab0-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="72ab0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72ab0-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="72ab0-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72ab0-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ab0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ab0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="72ab0-116">See also</span></span>

- [<span data-ttu-id="72ab0-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72ab0-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="72ab0-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72ab0-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
