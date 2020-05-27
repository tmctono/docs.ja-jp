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
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003946"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="e5f17-102">IMetaDataEmit::SetHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="e5f17-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="e5f17-103">指定したポインターによって参照されるメソッドを、 `IUnknown` トークンリマップの通知コールバックとして設定します。</span><span class="sxs-lookup"><span data-stu-id="e5f17-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f17-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5f17-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f17-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5f17-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="e5f17-106">から登録するハンドラー。</span><span class="sxs-lookup"><span data-stu-id="e5f17-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5f17-107">コメント</span><span class="sxs-lookup"><span data-stu-id="e5f17-107">Remarks</span></span>  
 <span data-ttu-id="e5f17-108">メタデータエンジンは、によって提供されるメソッドを使用して、最適化された `SetHandler` 方法でレコードを生成せず、保存されたレコードを最適化するコンパイラに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="e5f17-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="e5f17-109">コールバックメソッドがによって提供されていない場合 `SetHandler` 、 `IMapToken` 各スコープに対して merge on merge を使用して複数のインポートスコープがマージされている場合を除き、保存時に最適化は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e5f17-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f17-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5f17-110">Requirements</span></span>  
 <span data-ttu-id="e5f17-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f17-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f17-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e5f17-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5f17-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5f17-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5f17-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f17-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5f17-115">See also</span></span>

- [<span data-ttu-id="e5f17-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5f17-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e5f17-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5f17-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
