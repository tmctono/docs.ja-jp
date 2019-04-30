---
title: IMetaDataEmit::SetFieldRVA メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992473"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="edde7-102">IMetaDataEmit::SetFieldRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="edde7-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="edde7-103">指定したトークンによって参照されるフィールドの相対仮想アドレスのグローバル変数の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="edde7-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edde7-104">構文</span><span class="sxs-lookup"><span data-stu-id="edde7-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edde7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="edde7-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="edde7-106">[in]対象フィールドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="edde7-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="edde7-107">[in]コードまたはデータ領域のアドレス。</span><span class="sxs-lookup"><span data-stu-id="edde7-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edde7-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="edde7-108">Requirements</span></span>  
 <span data-ttu-id="edde7-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edde7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edde7-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="edde7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edde7-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="edde7-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edde7-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edde7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edde7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="edde7-113">See also</span></span>

- [<span data-ttu-id="edde7-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edde7-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="edde7-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edde7-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
