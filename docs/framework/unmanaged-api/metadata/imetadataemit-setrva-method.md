---
title: IMetaDataEmit::SetRVA メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: fe0b4b7fef0d05c4acc06dad5bc8a4eaf0722c9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175578"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="224a4-102">IMetaDataEmit::SetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="224a4-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="224a4-103">指定したメソッドの相対仮想アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="224a4-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="224a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="224a4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="224a4-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="224a4-106">[in]ターゲット メソッドまたはメソッド実装のトークン。</span><span class="sxs-lookup"><span data-stu-id="224a4-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="224a4-107">[in]コードまたはデータ域のアドレス。</span><span class="sxs-lookup"><span data-stu-id="224a4-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="224a4-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="224a4-108">Requirements</span></span>  
 <span data-ttu-id="224a4-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="224a4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="224a4-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="224a4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="224a4-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="224a4-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="224a4-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="224a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224a4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="224a4-113">See also</span></span>

- [<span data-ttu-id="224a4-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="224a4-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="224a4-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="224a4-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
