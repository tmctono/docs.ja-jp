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
ms.openlocfilehash: b8755629cca27784609de8166dddf44ed1c82bdc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432542"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="23a59-102">IMetaDataEmit::SetMethodImplFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="23a59-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="23a59-103">指定したトークンによって参照される、継承されたメソッドの実装のメタデータシグネチャを設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="23a59-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a59-104">構文</span><span class="sxs-lookup"><span data-stu-id="23a59-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23a59-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23a59-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="23a59-106">から変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="23a59-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="23a59-107">からメソッド実装機能を指定する[Cormethodimpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列挙値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="23a59-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23a59-108">要件</span><span class="sxs-lookup"><span data-stu-id="23a59-108">Requirements</span></span>  
 <span data-ttu-id="23a59-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23a59-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23a59-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="23a59-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23a59-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="23a59-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23a59-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23a59-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a59-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="23a59-113">See also</span></span>

- [<span data-ttu-id="23a59-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23a59-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="23a59-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23a59-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
