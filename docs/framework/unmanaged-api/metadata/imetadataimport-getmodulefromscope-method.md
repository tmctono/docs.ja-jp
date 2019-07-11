---
title: IMetaDataImport::GetModuleFromScope メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ce699669095e9c0b45882b18a01ec326640038
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779011"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="1c26e-102">IMetaDataImport::GetModuleFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="1c26e-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="1c26e-103">現在のメタデータ スコープ内で参照されるモジュールのメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c26e-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c26e-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c26e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c26e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c26e-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="1c26e-106">[out]現在のメタデータ スコープで参照されているモジュールを表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1c26e-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c26e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c26e-107">Requirements</span></span>  
 <span data-ttu-id="1c26e-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c26e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c26e-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c26e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c26e-110">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1c26e-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c26e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c26e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c26e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c26e-112">See also</span></span>

- [<span data-ttu-id="1c26e-113">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c26e-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1c26e-114">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c26e-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
