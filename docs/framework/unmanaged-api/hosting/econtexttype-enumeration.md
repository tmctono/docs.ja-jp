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
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493418"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="a6ab6-102">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a6ab6-102">EContextType Enumeration</span></span>
<span data-ttu-id="a6ab6-103">現在実行中のスレッドのセキュリティコンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="a6ab6-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ab6-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6ab6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="a6ab6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6ab6-105">Members</span></span>  
  
|<span data-ttu-id="a6ab6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6ab6-106">Member</span></span>|<span data-ttu-id="a6ab6-107">説明</span><span class="sxs-lookup"><span data-stu-id="a6ab6-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="a6ab6-108">共通言語ランタイム (CLR) が[IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)メソッドを呼び出す時点での現在のスレッドのコンテキスト、または[IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md)メソッドの呼び出しで CLR によって要求されたコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="a6ab6-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="a6ab6-109">ホストが低い特権 (ガベージコレクター、クラスまたはモジュールコンストラクターなど) を持つコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="a6ab6-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ab6-110">解説</span><span class="sxs-lookup"><span data-stu-id="a6ab6-110">Remarks</span></span>  
 <span data-ttu-id="a6ab6-111">CLR は、 `EContextType` メソッドとメソッドの呼び出しで、値の1つをパラメーター値として提供し `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` ます。</span><span class="sxs-lookup"><span data-stu-id="a6ab6-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ab6-112">要件</span><span class="sxs-lookup"><span data-stu-id="a6ab6-112">Requirements</span></span>  
 <span data-ttu-id="a6ab6-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ab6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ab6-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a6ab6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6ab6-115">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a6ab6-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6ab6-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ab6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ab6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6ab6-117">See also</span></span>

- [<span data-ttu-id="a6ab6-118">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6ab6-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a6ab6-119">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6ab6-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a6ab6-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="a6ab6-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
