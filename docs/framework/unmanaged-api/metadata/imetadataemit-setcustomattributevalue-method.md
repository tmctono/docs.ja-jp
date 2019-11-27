---
title: IMetaDataEmit::SetCustomAttributeValue メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: fd5e71071de9e6afebc8f1848e0af8835f22c9bf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448123"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="863ef-102">IMetaDataEmit::SetCustomAttributeValue メソッド</span><span class="sxs-lookup"><span data-stu-id="863ef-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="863ef-103">[IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)の前の呼び出しで定義されたカスタム属性の値を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="863ef-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="863ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="863ef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="863ef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="863ef-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="863ef-106">から対象のカスタム属性のトークン。</span><span class="sxs-lookup"><span data-stu-id="863ef-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="863ef-107">からカスタム属性を格納している配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="863ef-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="863ef-108">からカスタム属性のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="863ef-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="863ef-109">要件</span><span class="sxs-lookup"><span data-stu-id="863ef-109">Requirements</span></span>  
 <span data-ttu-id="863ef-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="863ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="863ef-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="863ef-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="863ef-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="863ef-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="863ef-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="863ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863ef-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="863ef-114">See also</span></span>

- [<span data-ttu-id="863ef-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="863ef-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="863ef-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="863ef-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
