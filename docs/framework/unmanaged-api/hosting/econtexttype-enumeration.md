---
title: EContextType 列挙型
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131146"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="9e684-102">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="9e684-102">EContextType Enumeration</span></span>
<span data-ttu-id="9e684-103">現在実行中のスレッドのセキュリティコンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="9e684-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e684-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e684-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="9e684-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e684-105">Members</span></span>  
  
|<span data-ttu-id="9e684-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e684-106">Member</span></span>|<span data-ttu-id="9e684-107">説明</span><span class="sxs-lookup"><span data-stu-id="9e684-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="9e684-108">共通言語ランタイム (CLR) が[IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)メソッドを呼び出す時点での現在のスレッドのコンテキスト、または[IHostSecurityManager:: SetSecurityContext の呼び出しで CLR によって要求されたコンテキストを示します。](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="9e684-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="9e684-109">ホストが低い特権 (ガベージコレクター、クラスまたはモジュールコンストラクターなど) を持つコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="9e684-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e684-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e684-110">Remarks</span></span>  
 <span data-ttu-id="9e684-111">CLR は、`IHostSecurityManager::GetSecurityContext` メソッドと `IHostSecurityManager::SetSecurityContext` メソッドの呼び出しで、`EContextType` の値の1つをパラメーター値として提供します。</span><span class="sxs-lookup"><span data-stu-id="9e684-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e684-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="9e684-112">Requirements</span></span>  
 <span data-ttu-id="9e684-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e684-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e684-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e684-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e684-115">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e684-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e684-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e684-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e684-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e684-117">See also</span></span>

- [<span data-ttu-id="9e684-118">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e684-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="9e684-119">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e684-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="9e684-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="9e684-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
