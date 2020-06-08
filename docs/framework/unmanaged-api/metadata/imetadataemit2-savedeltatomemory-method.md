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
ms.openlocfilehash: 8a6f11996425c92d9b0e3123ee2d3a064739454b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492760"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="e7a3d-102">IMetaDataEmit2::SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="e7a3d-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="e7a3d-103">現在のエディットコンティニュセッションの変更をメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7a3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7a3d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7a3d-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="e7a3d-106">入出力メタデータデルタの書き込みを開始するアドレス。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="e7a3d-107">から変更のサイズ。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-107">[in] The size of the changes.</span></span> <span data-ttu-id="e7a3d-108">サイズを確認するには、 [IMetaDataEmit2:: GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a3d-109">要件</span><span class="sxs-lookup"><span data-stu-id="e7a3d-109">Requirements</span></span>  
 <span data-ttu-id="e7a3d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a3d-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e7a3d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7a3d-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a3d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7a3d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a3d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a3d-114">See also</span></span>

- [<span data-ttu-id="e7a3d-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7a3d-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="e7a3d-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7a3d-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
