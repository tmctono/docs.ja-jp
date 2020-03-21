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
ms.openlocfilehash: 7ed7770f26ea4620d79f3be3f67e72f73c75057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175630"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="29f43-102">IMetaDataEmit::SetMethodImplFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="29f43-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="29f43-103">指定したトークンによって参照される継承されたメソッド実装のメタデータ シグネチャを設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="29f43-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f43-104">構文</span><span class="sxs-lookup"><span data-stu-id="29f43-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29f43-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29f43-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="29f43-106">[in]変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="29f43-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="29f43-107">[in]メソッド実装機能を指定する[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列挙型の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="29f43-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29f43-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="29f43-108">Requirements</span></span>  
 <span data-ttu-id="29f43-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f43-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f43-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="29f43-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29f43-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="29f43-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29f43-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29f43-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f43-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="29f43-113">See also</span></span>

- [<span data-ttu-id="29f43-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29f43-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="29f43-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29f43-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
