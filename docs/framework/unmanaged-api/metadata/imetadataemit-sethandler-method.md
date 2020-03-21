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
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177541"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="1aef2-102">IMetaDataEmit::SetHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="1aef2-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="1aef2-103">トークンの再マップの通知コールバックとして`IUnknown`、指定したポインターによって参照されるメソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="1aef2-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aef2-104">構文</span><span class="sxs-lookup"><span data-stu-id="1aef2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aef2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1aef2-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="1aef2-106">[in]登録するハンドラー。</span><span class="sxs-lookup"><span data-stu-id="1aef2-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aef2-107">解説</span><span class="sxs-lookup"><span data-stu-id="1aef2-107">Remarks</span></span>  
 <span data-ttu-id="1aef2-108">メタデータ エンジンは、 によって`SetHandler`提供されるメソッドを使用して、最適化された方法でレコードを生成せず、保存されたレコードを最適化するコンパイラに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="1aef2-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="1aef2-109">コールバック メソッドが を通じて`SetHandler`提供されない場合、各スコープのマージ時に複数のインポート スコープがマージされている`IMapToken`場合を除き、save で最適化は実行されません。</span><span class="sxs-lookup"><span data-stu-id="1aef2-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aef2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1aef2-110">Requirements</span></span>  
 <span data-ttu-id="1aef2-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aef2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aef2-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="1aef2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1aef2-113">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="1aef2-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aef2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aef2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aef2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aef2-115">See also</span></span>

- [<span data-ttu-id="1aef2-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aef2-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1aef2-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aef2-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
