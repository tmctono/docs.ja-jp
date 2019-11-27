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
ms.openlocfilehash: 9d0f443b5b7d2d358534e888c3fc84ad3f554119
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450045"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="39a97-102">IMetaDataImport::EnumPermissionSets メソッド</span><span class="sxs-lookup"><span data-stu-id="39a97-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="39a97-103">指定したメタデータ スコープ内のオブジェクトのアクセス許可を列挙します。</span><span class="sxs-lookup"><span data-stu-id="39a97-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a97-104">構文</span><span class="sxs-lookup"><span data-stu-id="39a97-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="39a97-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39a97-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="39a97-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="39a97-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="39a97-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a97-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="39a97-108">から検索範囲を制限するメタデータトークン。または、可能な限り広い範囲を検索する場合は NULL。</span><span class="sxs-lookup"><span data-stu-id="39a97-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="39a97-109">から`rPermission`に含める <xref:System.Security.Permissions.SecurityAction> 値を表すフラグ。すべてのアクションを返す場合は0。</span><span class="sxs-lookup"><span data-stu-id="39a97-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="39a97-110">入出力アクセス許可トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="39a97-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="39a97-111">[in] `rPermission` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="39a97-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="39a97-112">入出力`rPermission`で返されるアクセス許可トークンの数。</span><span class="sxs-lookup"><span data-stu-id="39a97-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39a97-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="39a97-113">Return Value</span></span>  
  
|<span data-ttu-id="39a97-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39a97-114">HRESULT</span></span>|<span data-ttu-id="39a97-115">説明</span><span class="sxs-lookup"><span data-stu-id="39a97-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="39a97-116">`EnumPermissionSets` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="39a97-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="39a97-117">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="39a97-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="39a97-118">この場合、`pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="39a97-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39a97-119">要件</span><span class="sxs-lookup"><span data-stu-id="39a97-119">Requirements</span></span>  
 <span data-ttu-id="39a97-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a97-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a97-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="39a97-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39a97-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="39a97-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39a97-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a97-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a97-124">参照</span><span class="sxs-lookup"><span data-stu-id="39a97-124">See also</span></span>

- [<span data-ttu-id="39a97-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a97-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="39a97-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a97-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
