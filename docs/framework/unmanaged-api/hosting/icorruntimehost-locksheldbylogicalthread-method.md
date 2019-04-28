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
ms.openlocfilehash: 90af015de4428f75330de89978a7fc0a4b26750b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700749"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="e6bf5-102">ICorRuntimeHost::LocksHeldByLogicalThread メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bf5-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="e6bf5-103">現在のスレッドを保持するロックの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6bf5-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="e6bf5-104">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="e6bf5-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6bf5-105">構文</span><span class="sxs-lookup"><span data-stu-id="e6bf5-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6bf5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6bf5-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="e6bf5-107">[out]現在のスレッドを保持するロックの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6bf5-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6bf5-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6bf5-108">Requirements</span></span>  
 <span data-ttu-id="e6bf5-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6bf5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6bf5-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6bf5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6bf5-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e6bf5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6bf5-112">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e6bf5-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bf5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6bf5-113">See also</span></span>

- [<span data-ttu-id="e6bf5-114">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6bf5-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
