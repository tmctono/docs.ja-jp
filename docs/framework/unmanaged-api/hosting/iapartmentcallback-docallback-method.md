---
title: IApartmentCallback::DoCallback メソッド
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80aa64a8867a84100996ae88c5e65233d6b15782
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481067"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="dc0b1-102">IApartmentCallback::DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="dc0b1-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="dc0b1-103">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b1-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc0b1-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc0b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc0b1-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="dc0b1-106">[in]アパートメント内で実行される関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc0b1-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="dc0b1-107">[in]関数の引数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc0b1-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0b1-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc0b1-108">Requirements</span></span>  
 <span data-ttu-id="dc0b1-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0b1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc0b1-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc0b1-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc0b1-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dc0b1-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc0b1-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc0b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0b1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc0b1-113">See also</span></span>
- [<span data-ttu-id="dc0b1-114">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc0b1-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
