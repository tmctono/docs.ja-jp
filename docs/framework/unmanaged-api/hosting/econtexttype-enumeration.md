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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f93f36a78ff5579e131ef4bb3d48f04e806c14de
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779394"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="a40c4-102">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a40c4-102">EContextType Enumeration</span></span>
<span data-ttu-id="a40c4-103">現在実行中のスレッドのセキュリティ コンテキストをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a40c4-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="a40c4-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="a40c4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a40c4-105">Members</span></span>  
  
|<span data-ttu-id="a40c4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a40c4-106">Member</span></span>|<span data-ttu-id="a40c4-107">説明</span><span class="sxs-lookup"><span data-stu-id="a40c4-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="a40c4-108">共通言語ランタイム (CLR) の呼び出し時に、現在のスレッドのコンテキストを示す、 [ihostsecuritymanager::getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)メソッド、または CLR への呼び出しでは、によって要求されたコンテキスト、 [Ihostsecuritymanager::setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a40c4-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="a40c4-109">どのホストには、ガベージ コレクターまたはクラスまたはモジュールのコンス トラクターなどの低い特権コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="a40c4-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a40c4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a40c4-110">Remarks</span></span>  
 <span data-ttu-id="a40c4-111">いずれかの CLR が用意されて、`EContextType`値への呼び出しでパラメーター値として、`IHostSecurityManager::GetSecurityContext`と`IHostSecurityManager::SetSecurityContext`メソッド。</span><span class="sxs-lookup"><span data-stu-id="a40c4-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a40c4-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a40c4-112">Requirements</span></span>  
 <span data-ttu-id="a40c4-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a40c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40c4-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a40c4-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a40c4-115">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a40c4-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a40c4-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40c4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a40c4-117">See also</span></span>

- [<span data-ttu-id="a40c4-118">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a40c4-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a40c4-119">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a40c4-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a40c4-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="a40c4-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
