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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d12555fb53a6c1b21f161402da77860adcf0a4b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478909"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="d7a9a-102">ICorRuntimeHost::SwitchInLogicalThreadState メソッド</span><span class="sxs-lookup"><span data-stu-id="d7a9a-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="d7a9a-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="d7a9a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7a9a-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7a9a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7a9a-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="d7a9a-106">[in]ファイバーを使用することを示しますクッキー。</span><span class="sxs-lookup"><span data-stu-id="d7a9a-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a9a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7a9a-107">Requirements</span></span>  
 <span data-ttu-id="d7a9a-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7a9a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a9a-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7a9a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7a9a-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d7a9a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7a9a-111">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d7a9a-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a9a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7a9a-112">See also</span></span>
- [<span data-ttu-id="d7a9a-113">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7a9a-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
