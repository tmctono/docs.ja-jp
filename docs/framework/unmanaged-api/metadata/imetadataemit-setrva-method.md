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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02331bb3b0c70b946eaa28c9cd316f109ac927b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777236"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="ee3e0-102">IMetaDataEmit::SetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="ee3e0-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="ee3e0-103">指定したメソッドの相対仮想アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="ee3e0-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee3e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee3e0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee3e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee3e0-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ee3e0-106">[in]対象のメソッドまたはメソッドの実装のトークンです。</span><span class="sxs-lookup"><span data-stu-id="ee3e0-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="ee3e0-107">[in]コードまたはデータ領域のアドレス。</span><span class="sxs-lookup"><span data-stu-id="ee3e0-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee3e0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee3e0-108">Requirements</span></span>  
 <span data-ttu-id="ee3e0-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee3e0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee3e0-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee3e0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee3e0-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="ee3e0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee3e0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee3e0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3e0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee3e0-113">See also</span></span>

- [<span data-ttu-id="ee3e0-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee3e0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ee3e0-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee3e0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
