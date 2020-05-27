---
title: IMetaDataEmit::DeleteClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: 3ef6b89ed6578d77f30d5e53657b962b200b0ed6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009322"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="1bd9a-102">IMetaDataEmit::DeleteClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="1bd9a-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="1bd9a-103">指定したトークンによって表される型のクラスレイアウトメタデータシグネチャを破棄します。</span><span class="sxs-lookup"><span data-stu-id="1bd9a-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1bd9a-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bd9a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1bd9a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1bd9a-106">から`mdTypeDef`クラスレイアウトが削除される型を表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="1bd9a-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bd9a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="1bd9a-107">Requirements</span></span>  
 <span data-ttu-id="1bd9a-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bd9a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd9a-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="1bd9a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bd9a-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="1bd9a-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bd9a-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd9a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd9a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bd9a-112">See also</span></span>

- [<span data-ttu-id="1bd9a-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd9a-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1bd9a-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd9a-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
