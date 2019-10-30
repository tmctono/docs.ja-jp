---
title: ICorRuntimeHost::SwitchInLogicalThreadState メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133377"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="55569-102">ICorRuntimeHost::SwitchInLogicalThreadState メソッド</span><span class="sxs-lookup"><span data-stu-id="55569-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="55569-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="55569-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55569-104">構文</span><span class="sxs-lookup"><span data-stu-id="55569-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55569-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55569-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="55569-106">から使用するファイバーを示すクッキー。</span><span class="sxs-lookup"><span data-stu-id="55569-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55569-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="55569-107">Requirements</span></span>  
 <span data-ttu-id="55569-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55569-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55569-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="55569-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55569-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="55569-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55569-111">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="55569-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55569-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="55569-112">See also</span></span>

- [<span data-ttu-id="55569-113">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55569-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
