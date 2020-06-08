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
ms.openlocfilehash: 4e2b2501b6b7117cefcfa43511ef20f25106bb42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503587"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="96079-102">IMetaDataImport::GetModuleFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="96079-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="96079-103">現在のメタデータスコープで参照されているモジュールのメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="96079-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96079-104">構文</span><span class="sxs-lookup"><span data-stu-id="96079-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96079-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96079-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="96079-106">入出力現在のメタデータスコープで参照されているモジュールを表すトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="96079-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96079-107">要件</span><span class="sxs-lookup"><span data-stu-id="96079-107">Requirements</span></span>  
 <span data-ttu-id="96079-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96079-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96079-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="96079-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96079-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="96079-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96079-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96079-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96079-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="96079-112">See also</span></span>

- [<span data-ttu-id="96079-113">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96079-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="96079-114">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96079-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
