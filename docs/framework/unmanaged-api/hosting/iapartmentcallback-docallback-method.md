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
ms.openlocfilehash: 1a56c3ebe4b1c528f9c6555bdfbf1270a438410d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617114"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="5f237-102">IApartmentCallback::DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="5f237-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="5f237-103">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f237-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f237-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f237-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f237-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f237-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="5f237-106">からアパートメント内で実行される関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5f237-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="5f237-107">から関数の引数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5f237-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f237-108">要件</span><span class="sxs-lookup"><span data-stu-id="5f237-108">Requirements</span></span>  
 <span data-ttu-id="5f237-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f237-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f237-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f237-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f237-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5f237-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f237-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f237-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f237-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f237-113">See also</span></span>

- [<span data-ttu-id="5f237-114">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f237-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
