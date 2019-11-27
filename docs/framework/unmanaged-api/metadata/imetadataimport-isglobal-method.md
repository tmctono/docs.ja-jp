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
ms.openlocfilehash: 8a5dda5861343865a139f6b6b9e2794179b0727a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434718"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="0f144-102">IMetaDataImport::IsGlobal メソッド</span><span class="sxs-lookup"><span data-stu-id="0f144-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="0f144-103">指定したメタデータ トークンによって表されるフィールド、メソッド、または型がグローバル スコープを保持しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f144-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f144-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f144-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f144-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f144-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="0f144-106">から型、フィールド、またはメソッドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="0f144-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="0f144-107">[out] 1: オブジェクトにグローバルスコープがある場合は、それ以外の場合は 0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="0f144-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f144-108">要件</span><span class="sxs-lookup"><span data-stu-id="0f144-108">Requirements</span></span>  
 <span data-ttu-id="0f144-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f144-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f144-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0f144-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f144-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0f144-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f144-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f144-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f144-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f144-113">See also</span></span>

- [<span data-ttu-id="0f144-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f144-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f144-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f144-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
