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
ms.openlocfilehash: 9bb257a3d84d5022b9ae13c89a34572485d3033b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126945"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="103d1-102">IApartmentCallback::DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="103d1-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="103d1-103">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="103d1-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="103d1-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="103d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="103d1-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="103d1-106">からアパートメント内で実行される関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="103d1-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="103d1-107">から関数の引数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="103d1-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="103d1-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="103d1-108">Requirements</span></span>  
 <span data-ttu-id="103d1-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="103d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="103d1-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="103d1-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="103d1-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="103d1-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="103d1-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="103d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103d1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="103d1-113">See also</span></span>

- [<span data-ttu-id="103d1-114">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="103d1-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
