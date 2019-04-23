---
title: ICLRPolicyManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eeccc4dfd7a7147fe791444eeeca2bd3a844305
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211050"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="24ddd-102">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24ddd-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="24ddd-103">ホスト ポリシー エラーやタイムアウトが発生した場合に実行されるアクションを指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24ddd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-104">Methods</span></span>  
  
|<span data-ttu-id="24ddd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-105">Method</span></span>|<span data-ttu-id="24ddd-106">説明</span><span class="sxs-lookup"><span data-stu-id="24ddd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24ddd-107">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="24ddd-108">共通言語ランタイム (CLR) が指定したエラーが発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="24ddd-109">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="24ddd-110">指定された操作がタイムアウトしたときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="24ddd-111">SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="24ddd-112">指定された操作が発生したときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="24ddd-113">SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="24ddd-114">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="24ddd-115">SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="24ddd-116">指定された操作のタイムアウト値を設定し、操作が発生したときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="24ddd-117">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="24ddd-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="24ddd-118">ハンドルされない例外が発生したときに、CLR の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="24ddd-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24ddd-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="24ddd-119">Requirements</span></span>  
 <span data-ttu-id="24ddd-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24ddd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ddd-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24ddd-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24ddd-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="24ddd-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24ddd-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ddd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ddd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="24ddd-124">See also</span></span>

- [<span data-ttu-id="24ddd-125">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="24ddd-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="24ddd-126">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="24ddd-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="24ddd-127">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="24ddd-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="24ddd-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24ddd-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
