---
title: IMetaDataImport::IsGlobal メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: d477976952d2c1875a620d1397fd43e5c5e2836f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503472"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="f98f1-102">IMetaDataImport::IsGlobal メソッド</span><span class="sxs-lookup"><span data-stu-id="f98f1-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="f98f1-103">指定したメタデータ トークンによって表されるフィールド、メソッド、または型がグローバル スコープを保持しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f98f1-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f98f1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f98f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f98f1-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="f98f1-106">から型、フィールド、またはメソッドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="f98f1-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="f98f1-107">[out] 1: オブジェクトにグローバルスコープがある場合は、それ以外の場合は 0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="f98f1-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f98f1-108">要件</span><span class="sxs-lookup"><span data-stu-id="f98f1-108">Requirements</span></span>  
 <span data-ttu-id="f98f1-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f98f1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f98f1-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f98f1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f98f1-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f98f1-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f98f1-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f98f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98f1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f98f1-113">See also</span></span>

- [<span data-ttu-id="f98f1-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f98f1-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f98f1-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f98f1-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
