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
ms.openlocfilehash: e18172ecf2d4300ae42cc42ecdb1783744cac105
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490419"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="5b209-102">GetCLRIdentityManager 関数</span><span class="sxs-lookup"><span data-stu-id="5b209-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="5b209-103">共通言語ランタイム (CLR) ユーザーの管理に使用するインターフェイスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b209-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="5b209-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="5b209-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b209-105">構文</span><span class="sxs-lookup"><span data-stu-id="5b209-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b209-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b209-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="5b209-107">[in]A `REFIID` (インターフェイス識別子) を取得するには、どのインターフェイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b209-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="5b209-108">この値は、IID_ICLRAssemblyIdentityManager または IID_ICLRHostBindingPolicyManager のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b209-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="5b209-109">[out]どちらのアドレスへのポインター、 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)または[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5b209-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b209-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b209-110">Remarks</span></span>  
 <span data-ttu-id="5b209-111">呼び出す、 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)へのポインターを取得する関数、`GetCLRIdentityManager`関数。</span><span class="sxs-lookup"><span data-stu-id="5b209-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b209-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b209-112">Requirements</span></span>  
 <span data-ttu-id="5b209-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b209-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b209-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b209-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b209-115">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="5b209-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5b209-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b209-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b209-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b209-117">See also</span></span>

- [<span data-ttu-id="5b209-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="5b209-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
