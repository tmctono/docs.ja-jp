---
title: EClrUnhandledException 列挙型
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba0c2ea7733f098b7fac95f51b5eb16d083174e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779368"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="4209d-102">EClrUnhandledException 列挙型</span><span class="sxs-lookup"><span data-stu-id="4209d-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="4209d-103">ユーザー コードでハンドルされない例外を管理するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4209d-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4209d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4209d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="4209d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4209d-105">Members</span></span>  
  
|<span data-ttu-id="4209d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4209d-106">Member</span></span>|<span data-ttu-id="4209d-107">説明</span><span class="sxs-lookup"><span data-stu-id="4209d-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="4209d-108">既定の動作が発生したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4209d-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="4209d-109">プロセスは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="4209d-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="4209d-110">共通言語ランタイム (CLR) はハンドルされない例外は無視され、により、さらにアクションを決定するホストを指定します。</span><span class="sxs-lookup"><span data-stu-id="4209d-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4209d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4209d-111">Remarks</span></span>  
 <span data-ttu-id="4209d-112">CLR は、以前のバージョンのように動作を指定するには、使用、`eHostDeterminedPolicy`メンバー。</span><span class="sxs-lookup"><span data-stu-id="4209d-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4209d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4209d-113">Requirements</span></span>  
 <span data-ttu-id="4209d-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4209d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4209d-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4209d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4209d-116">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4209d-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4209d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4209d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4209d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4209d-118">See also</span></span>

- [<span data-ttu-id="4209d-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="4209d-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="4209d-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="4209d-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="4209d-121">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4209d-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="4209d-122">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="4209d-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="4209d-123">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4209d-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="4209d-124">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="4209d-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
