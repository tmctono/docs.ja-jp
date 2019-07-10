---
title: GetCLRIdentityManager 関数
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ea4947582e4e8bfdb6873a90c5284e9ae9d8a62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736243"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="74077-102">GetCLRIdentityManager 関数</span><span class="sxs-lookup"><span data-stu-id="74077-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="74077-103">共通言語ランタイム (CLR) ユーザーの管理に使用するインターフェイスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="74077-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="74077-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="74077-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74077-105">構文</span><span class="sxs-lookup"><span data-stu-id="74077-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74077-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74077-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="74077-107">[in]A `REFIID` (インターフェイス識別子) を取得するには、どのインターフェイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="74077-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="74077-108">この値は、IID_ICLRAssemblyIdentityManager または IID_ICLRHostBindingPolicyManager のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="74077-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="74077-109">[out]どちらのアドレスへのポインター、 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)または[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="74077-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74077-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="74077-110">Remarks</span></span>  
 <span data-ttu-id="74077-111">呼び出す、 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)へのポインターを取得する関数、`GetCLRIdentityManager`関数。</span><span class="sxs-lookup"><span data-stu-id="74077-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74077-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="74077-112">Requirements</span></span>  
 <span data-ttu-id="74077-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74077-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74077-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74077-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74077-115">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="74077-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="74077-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74077-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74077-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="74077-117">See also</span></span>

- [<span data-ttu-id="74077-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="74077-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
