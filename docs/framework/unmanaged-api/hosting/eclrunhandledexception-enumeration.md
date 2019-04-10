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
ms.openlocfilehash: 7e5fb3ab1d2dedb220fd4a486409512414233021
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176671"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="c8aa3-102">EClrUnhandledException 列挙型</span><span class="sxs-lookup"><span data-stu-id="c8aa3-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="c8aa3-103">ユーザー コードでハンドルされない例外を管理するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8aa3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8aa3-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="c8aa3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8aa3-105">Members</span></span>  
  
|<span data-ttu-id="c8aa3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8aa3-106">Member</span></span>|<span data-ttu-id="c8aa3-107">説明</span><span class="sxs-lookup"><span data-stu-id="c8aa3-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="c8aa3-108">既定の動作が発生したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="c8aa3-109">プロセスは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="c8aa3-110">共通言語ランタイム (CLR) はハンドルされない例外は無視され、により、さらにアクションを決定するホストを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8aa3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8aa3-111">Remarks</span></span>  
 <span data-ttu-id="c8aa3-112">CLR は、以前のバージョンのように動作を指定するには、使用、`eHostDeterminedPolicy`メンバー。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8aa3-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8aa3-113">Requirements</span></span>  
 <span data-ttu-id="c8aa3-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8aa3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8aa3-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8aa3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8aa3-116">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8aa3-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c8aa3-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c8aa3-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8aa3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8aa3-118">See also</span></span>

- [<span data-ttu-id="c8aa3-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="c8aa3-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="c8aa3-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="c8aa3-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="c8aa3-121">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8aa3-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="c8aa3-122">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="c8aa3-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="c8aa3-123">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8aa3-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="c8aa3-124">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="c8aa3-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
