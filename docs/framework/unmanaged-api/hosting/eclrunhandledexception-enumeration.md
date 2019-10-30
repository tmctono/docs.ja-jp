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
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131232"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="d2b17-102">EClrUnhandledException 列挙型</span><span class="sxs-lookup"><span data-stu-id="d2b17-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="d2b17-103">ユーザーコードで処理されない例外を管理するために使用できるオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d2b17-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b17-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2b17-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="d2b17-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d2b17-105">Members</span></span>  
  
|<span data-ttu-id="d2b17-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d2b17-106">Member</span></span>|<span data-ttu-id="d2b17-107">説明</span><span class="sxs-lookup"><span data-stu-id="d2b17-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="d2b17-108">既定の動作を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b17-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="d2b17-109">プロセスが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d2b17-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="d2b17-110">共通言語ランタイム (CLR) が未処理の例外を無視し、ホストがそれ以上のアクションを決定できるように指定します。</span><span class="sxs-lookup"><span data-stu-id="d2b17-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2b17-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2b17-111">Remarks</span></span>  
 <span data-ttu-id="d2b17-112">CLR が以前のバージョンと同じように動作するように指定するには、`eHostDeterminedPolicy` メンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2b17-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b17-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="d2b17-113">Requirements</span></span>  
 <span data-ttu-id="d2b17-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2b17-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b17-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2b17-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2b17-116">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2b17-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2b17-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b17-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b17-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2b17-118">See also</span></span>

- [<span data-ttu-id="d2b17-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="d2b17-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="d2b17-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="d2b17-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="d2b17-121">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2b17-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d2b17-122">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="d2b17-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="d2b17-123">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2b17-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="d2b17-124">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="d2b17-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
