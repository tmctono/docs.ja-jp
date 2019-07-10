---
title: ICorThreadpool::CorRegisterWaitForSingleObject メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorRegisterWaitForSingleObject
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegisterWaitForSingleObject
helpviewer_keywords:
- ICorThreadpool::CorRegisterWaitForSingleObject method [.NET Framework hosting]
- CorRegisterWaitForSingleObject method [.NET Framework hosting]
ms.assetid: cade1feb-71d2-43ed-85ca-7b2e9da12994
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2da8f5326bcd7f2c25c79027bb8a980e7d17e72
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751181"
---
# <a name="icorthreadpoolcorregisterwaitforsingleobject-method"></a><span data-ttu-id="02407-102">ICorThreadpool::CorRegisterWaitForSingleObject メソッド</span><span class="sxs-lookup"><span data-stu-id="02407-102">ICorThreadpool::CorRegisterWaitForSingleObject Method</span></span>
<span data-ttu-id="02407-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="02407-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02407-104">構文</span><span class="sxs-lookup"><span data-stu-id="02407-104">Syntax</span></span>  
  
```cpp  
HRESULT CorRegisterWaitForSingleObject (  
    [in]  HANDLE*             phNewWaitObject,  
    [in]  HANDLE              hWaitObject,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Context,  
    [in]  ULONG               timeout,  
    [in]  BOOL                executeOnlyOnce,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="02407-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="02407-105">Requirements</span></span>  
 <span data-ttu-id="02407-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02407-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02407-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02407-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02407-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="02407-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02407-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02407-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02407-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="02407-110">See also</span></span>

- [<span data-ttu-id="02407-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02407-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
