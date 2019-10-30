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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140802"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="9db31-102">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9db31-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="9db31-103">エラーやタイムアウトが発生した場合に実行されるポリシーアクションをホストが指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9db31-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9db31-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-104">Methods</span></span>  
  
|<span data-ttu-id="9db31-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-105">Method</span></span>|<span data-ttu-id="9db31-106">説明</span><span class="sxs-lookup"><span data-stu-id="9db31-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9db31-107">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="9db31-108">指定したエラーが発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="9db31-109">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="9db31-110">指定された操作がタイムアウトしたときに CLR が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="9db31-111">SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="9db31-112">指定された操作が発生したときに CLR が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="9db31-113">SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="9db31-114">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="9db31-115">SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="9db31-116">指定された操作のタイムアウト値を設定し、操作が発生したときに CLR が実行する必要があるポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="9db31-117">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="9db31-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="9db31-118">未処理の例外が発生した場合の CLR の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="9db31-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9db31-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="9db31-119">Requirements</span></span>  
 <span data-ttu-id="9db31-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db31-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db31-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9db31-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9db31-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9db31-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9db31-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9db31-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db31-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9db31-124">See also</span></span>

- [<span data-ttu-id="9db31-125">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="9db31-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="9db31-126">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="9db31-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="9db31-127">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="9db31-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="9db31-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9db31-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
