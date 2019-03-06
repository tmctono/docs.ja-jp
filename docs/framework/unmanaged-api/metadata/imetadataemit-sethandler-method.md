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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ada84df2a08b992aa178c2fb63c713b05a8937a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503217"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="72f13-102">IMetaDataEmit::SetHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="72f13-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="72f13-103">指定したによって参照されるメソッドを設定`IUnknown`トークンを再マップの通知コールバックとしてのポインター。</span><span class="sxs-lookup"><span data-stu-id="72f13-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f13-104">構文</span><span class="sxs-lookup"><span data-stu-id="72f13-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72f13-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="72f13-106">[in]登録ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="72f13-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72f13-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="72f13-107">Remarks</span></span>  
 <span data-ttu-id="72f13-108">メタデータ エンジンによって提供されるメソッドを使用して通知を送信する`SetHandler`、最適化された方法でレコードを生成しないと、保存されたレコードを最適化するには、コンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="72f13-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="72f13-109">を介して、コールバック メソッドが提供されていない場合`SetHandler`、最適化は実行されませんで保存さまざまなインポートを除くスコープがマージされたを使用して`IMapToken`でスコープごとにマージします。</span><span class="sxs-lookup"><span data-stu-id="72f13-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f13-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="72f13-110">Requirements</span></span>  
 <span data-ttu-id="72f13-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f13-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f13-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72f13-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72f13-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="72f13-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72f13-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f13-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="72f13-115">See also</span></span>
- [<span data-ttu-id="72f13-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72f13-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="72f13-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72f13-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
