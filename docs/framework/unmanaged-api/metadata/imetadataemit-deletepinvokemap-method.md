---
title: IMetaDataEmit::DeletePinvokeMap メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 45f40dcd419e8e2fdf8a3349ccc9461854ad9aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175734"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="fcfbf-102">IMetaDataEmit::DeletePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="fcfbf-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="fcfbf-103">指定したトークンによって参照されるオブジェクトの PInvoke マッピング メタデータを破棄します。</span><span class="sxs-lookup"><span data-stu-id="fcfbf-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcfbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcfbf-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcfbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcfbf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fcfbf-106">[in]PInvoke マッピング メタデータを削除する対象のオブジェクトを表す`mdFieldDef`トークン`mdMethodDef`。</span><span class="sxs-lookup"><span data-stu-id="fcfbf-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcfbf-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcfbf-107">Requirements</span></span>  
 <span data-ttu-id="fcfbf-108">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcfbf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcfbf-109">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fcfbf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fcfbf-110">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcfbf-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcfbf-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcfbf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfbf-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcfbf-112">See also</span></span>

- [<span data-ttu-id="fcfbf-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcfbf-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fcfbf-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcfbf-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
