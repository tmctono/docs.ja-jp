---
title: IMetaDataEmit::SetHandler メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442155"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="71525-102">IMetaDataEmit::SetHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="71525-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="71525-103">指定した `IUnknown` ポインターによって参照されるメソッドを、トークンリマップの通知コールバックとして設定します。</span><span class="sxs-lookup"><span data-stu-id="71525-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71525-104">構文</span><span class="sxs-lookup"><span data-stu-id="71525-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71525-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71525-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="71525-106">から登録するハンドラー。</span><span class="sxs-lookup"><span data-stu-id="71525-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71525-107">コメント</span><span class="sxs-lookup"><span data-stu-id="71525-107">Remarks</span></span>  
 <span data-ttu-id="71525-108">メタデータエンジンは、`SetHandler`によって提供されるメソッドを使用して、最適化された方法でレコードを生成せず、保存されたレコードを最適化するコンパイラに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="71525-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="71525-109">コールバックメソッドが `SetHandler`によって提供されていない場合、`IMapToken` を使用して複数のインポートスコープがマージされている場合を除き、保存時に最適化は実行されません。</span><span class="sxs-lookup"><span data-stu-id="71525-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71525-110">要件</span><span class="sxs-lookup"><span data-stu-id="71525-110">Requirements</span></span>  
 <span data-ttu-id="71525-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71525-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71525-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="71525-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71525-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="71525-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71525-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71525-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71525-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="71525-115">See also</span></span>

- [<span data-ttu-id="71525-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71525-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="71525-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71525-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
