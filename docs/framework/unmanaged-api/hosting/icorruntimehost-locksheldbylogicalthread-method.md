---
title: ICorRuntimeHost::LocksHeldByLogicalThread メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eed83cbc983d59e99b3a42e667e9e126316c263
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780098"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="daeea-102">ICorRuntimeHost::LocksHeldByLogicalThread メソッド</span><span class="sxs-lookup"><span data-stu-id="daeea-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="daeea-103">現在のスレッドを保持するロックの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="daeea-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="daeea-104">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="daeea-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daeea-105">構文</span><span class="sxs-lookup"><span data-stu-id="daeea-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daeea-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="daeea-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="daeea-107">[out]現在のスレッドを保持するロックの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="daeea-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daeea-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="daeea-108">Requirements</span></span>  
 <span data-ttu-id="daeea-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="daeea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daeea-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="daeea-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="daeea-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="daeea-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daeea-112">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="daeea-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daeea-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="daeea-113">See also</span></span>

- [<span data-ttu-id="daeea-114">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="daeea-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
