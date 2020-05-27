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
ms.openlocfilehash: 79af7b5679598ffa82471dcb69adabc2394b13fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009302"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="65507-102">IMetaDataEmit::DeletePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="65507-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="65507-103">指定したトークンによって参照されるオブジェクトの PInvoke マッピングメタデータを破棄します。</span><span class="sxs-lookup"><span data-stu-id="65507-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65507-104">構文</span><span class="sxs-lookup"><span data-stu-id="65507-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65507-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65507-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="65507-106">から`mdFieldDef` `mdMethodDef` PInvoke マッピングメタデータを削除する対象のオブジェクトを表すまたはトークン。</span><span class="sxs-lookup"><span data-stu-id="65507-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65507-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="65507-107">Requirements</span></span>  
 <span data-ttu-id="65507-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65507-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65507-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="65507-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65507-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="65507-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65507-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65507-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65507-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="65507-112">See also</span></span>

- [<span data-ttu-id="65507-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65507-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="65507-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65507-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
