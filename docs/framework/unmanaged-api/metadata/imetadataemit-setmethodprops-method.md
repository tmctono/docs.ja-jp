---
title: IMetaDataEmit::SetMethodProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 9662a14b4ea97aed16968083489324d46c38dda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177508"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="726c6-102">IMetaDataEmit::SetMethodProps メソッド</span><span class="sxs-lookup"><span data-stu-id="726c6-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="726c6-103">[IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)への以前の呼び出しで定義されたメソッドの、指定された相対仮想アドレスに格納されている機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="726c6-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="726c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="726c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="726c6-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="726c6-106">[in]変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="726c6-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="726c6-107">[in]メンバー属性。</span><span class="sxs-lookup"><span data-stu-id="726c6-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="726c6-108">[in]コードのアドレス。</span><span class="sxs-lookup"><span data-stu-id="726c6-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="726c6-109">[in]メソッドの実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="726c6-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="726c6-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="726c6-110">Requirements</span></span>  
 <span data-ttu-id="726c6-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="726c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726c6-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="726c6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="726c6-113">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="726c6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="726c6-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726c6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="726c6-115">See also</span></span>

- [<span data-ttu-id="726c6-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="726c6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="726c6-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="726c6-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
