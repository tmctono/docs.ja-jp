---
title: IMetaDataEmit2::SaveDeltaToMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 5ec4fe2a8e949cf6e9aa0ce68f4d4e49b72170b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177438"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="cb839-102">IMetaDataEmit2::SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="cb839-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="cb839-103">現在のエディット コンティニュ セッションの変更をメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="cb839-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb839-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb839-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb839-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb839-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="cb839-106">[アウト]メタデータ デルタの書き込みを開始するアドレス。</span><span class="sxs-lookup"><span data-stu-id="cb839-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="cb839-107">[in]変更のサイズ。</span><span class="sxs-lookup"><span data-stu-id="cb839-107">[in] The size of the changes.</span></span> <span data-ttu-id="cb839-108">サイズ[を決定するには、IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb839-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb839-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb839-109">Requirements</span></span>  
 <span data-ttu-id="cb839-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb839-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb839-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="cb839-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb839-112">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb839-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb839-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb839-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb839-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb839-114">See also</span></span>

- [<span data-ttu-id="cb839-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb839-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="cb839-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb839-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
