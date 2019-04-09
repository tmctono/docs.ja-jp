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
ms.openlocfilehash: e17a6846ba0276ec7ba423ab25e3f11baf278d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098755"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="a1574-102">IMetaDataEmit::SetRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="a1574-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="a1574-103">指定したメソッドの相対仮想アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1574-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1574-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1574-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1574-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1574-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a1574-106">[in]対象のメソッドまたはメソッドの実装のトークンです。</span><span class="sxs-lookup"><span data-stu-id="a1574-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="a1574-107">[in]コードまたはデータ領域のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a1574-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1574-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1574-108">Requirements</span></span>  
 <span data-ttu-id="a1574-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1574-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1574-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1574-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1574-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a1574-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a1574-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a1574-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1574-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1574-113">See also</span></span>

- [<span data-ttu-id="a1574-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1574-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a1574-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1574-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
