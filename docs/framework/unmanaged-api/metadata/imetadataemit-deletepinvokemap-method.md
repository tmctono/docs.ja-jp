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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64ba852c4bb0ae7b0119876fca4a4b2a107ed934
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777416"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="89a6f-102">IMetaDataEmit::DeletePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="89a6f-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="89a6f-103">指定したトークンによって参照されるオブジェクトの PInvoke マッピング メタデータを破棄します。</span><span class="sxs-lookup"><span data-stu-id="89a6f-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a6f-104">構文</span><span class="sxs-lookup"><span data-stu-id="89a6f-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89a6f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="89a6f-106">[in]`mdFieldDef`または`mdMethodDef`PInvoke マッピングのメタデータを削除するオブジェクトを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="89a6f-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a6f-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="89a6f-107">Requirements</span></span>  
 <span data-ttu-id="89a6f-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89a6f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a6f-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89a6f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89a6f-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="89a6f-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89a6f-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a6f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a6f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="89a6f-112">See also</span></span>

- [<span data-ttu-id="89a6f-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="89a6f-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="89a6f-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="89a6f-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
