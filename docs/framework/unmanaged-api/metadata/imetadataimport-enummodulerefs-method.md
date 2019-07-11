---
title: IMetaDataImport::EnumModuleRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afa2d35a193a11360b52bcbdc1d9e5dae16d1c90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782124"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="5eebc-102">IMetaDataImport::EnumModuleRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="5eebc-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="5eebc-103">インポートされたモジュールを表す ModuleRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5eebc-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eebc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5eebc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eebc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5eebc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5eebc-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5eebc-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5eebc-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="5eebc-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="5eebc-108">[out]ModuleRef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="5eebc-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5eebc-109">[in] `rModuleRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="5eebc-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="5eebc-110">[out]返される ModuleRef トークン数`rModuleRefs`します。</span><span class="sxs-lookup"><span data-stu-id="5eebc-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eebc-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="5eebc-111">Return Value</span></span>  
  
|<span data-ttu-id="5eebc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5eebc-112">HRESULT</span></span>|<span data-ttu-id="5eebc-113">説明</span><span class="sxs-lookup"><span data-stu-id="5eebc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5eebc-114">`EnumModuleRefs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="5eebc-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5eebc-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="5eebc-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5eebc-116">その場合は、`pcModuleRefs`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="5eebc-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5eebc-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="5eebc-117">Requirements</span></span>  
 <span data-ttu-id="5eebc-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eebc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eebc-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5eebc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5eebc-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5eebc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5eebc-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eebc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eebc-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5eebc-122">See also</span></span>

- [<span data-ttu-id="5eebc-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5eebc-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5eebc-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5eebc-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
