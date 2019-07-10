---
title: IMetaDataEmit::SetMethodImplFlags メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a437ff11114ea8d577b2fc3b81cd981cebb8c8d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751066"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="9757f-102">IMetaDataEmit::SetMethodImplFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="9757f-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="9757f-103">設定または指定したトークンによって参照されている継承されたメソッドの実装のメタデータ シグネチャを更新します。</span><span class="sxs-lookup"><span data-stu-id="9757f-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9757f-104">構文</span><span class="sxs-lookup"><span data-stu-id="9757f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9757f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9757f-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9757f-106">[in]変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="9757f-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="9757f-107">[in]値の組み合わせ、 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)メソッドの実装の機能を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="9757f-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9757f-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9757f-108">Requirements</span></span>  
 <span data-ttu-id="9757f-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9757f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9757f-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9757f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9757f-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9757f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9757f-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9757f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9757f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9757f-113">See also</span></span>

- [<span data-ttu-id="9757f-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9757f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9757f-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9757f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
