---
title: IObjectHandle::Unwrap メソッド
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
ms.openlocfilehash: 0ff088731514b2da0d8b1fa51ef48d8b71d16528
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842232"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="bb4e0-102">IObjectHandle::Unwrap メソッド</span><span class="sxs-lookup"><span data-stu-id="bb4e0-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="bb4e0-103">間接参照から値渡しのマーシャリングオブジェクトをラップ解除します。</span><span class="sxs-lookup"><span data-stu-id="bb4e0-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb4e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb4e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb4e0-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="bb4e0-106">入出力ラップを解除するオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bb4e0-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb4e0-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb4e0-107">Requirements</span></span>  
 <span data-ttu-id="bb4e0-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4e0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4e0-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bb4e0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb4e0-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bb4e0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb4e0-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
