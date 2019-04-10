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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211050"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="631fa-102">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="631fa-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="631fa-103">ホスト ポリシー エラーやタイムアウトが発生した場合に実行されるアクションを指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="631fa-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="631fa-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-104">Methods</span></span>  
  
|<span data-ttu-id="631fa-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-105">Method</span></span>|<span data-ttu-id="631fa-106">説明</span><span class="sxs-lookup"><span data-stu-id="631fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="631fa-107">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="631fa-108">共通言語ランタイム (CLR) が指定したエラーが発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="631fa-109">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="631fa-110">指定された操作がタイムアウトしたときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="631fa-111">SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="631fa-112">指定された操作が発生したときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="631fa-113">SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="631fa-114">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="631fa-115">SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="631fa-116">指定された操作のタイムアウト値を設定し、操作が発生したときに、CLR が実行ポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="631fa-117">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="631fa-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="631fa-118">ハンドルされない例外が発生したときに、CLR の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="631fa-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="631fa-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="631fa-119">Requirements</span></span>  
 <span data-ttu-id="631fa-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="631fa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631fa-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="631fa-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="631fa-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="631fa-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="631fa-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="631fa-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="631fa-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="631fa-124">See also</span></span>

- [<span data-ttu-id="631fa-125">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="631fa-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="631fa-126">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="631fa-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="631fa-127">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="631fa-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="631fa-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="631fa-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
