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
ms.openlocfilehash: 5ea100ff86286cb98db5aa9fa6f3c12f5d318a90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043130"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="578e8-102">IMetaDataEmit::DeletePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="578e8-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="578e8-103">指定したトークンによって参照されるオブジェクトの PInvoke マッピング メタデータを破棄します。</span><span class="sxs-lookup"><span data-stu-id="578e8-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="578e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="578e8-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="578e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="578e8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="578e8-106">[in]`mdFieldDef`または`mdMethodDef`PInvoke マッピングのメタデータを削除するオブジェクトを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="578e8-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="578e8-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="578e8-107">Requirements</span></span>  
 <span data-ttu-id="578e8-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="578e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="578e8-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="578e8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="578e8-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="578e8-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="578e8-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="578e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578e8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="578e8-112">See also</span></span>

- [<span data-ttu-id="578e8-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="578e8-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="578e8-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="578e8-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
