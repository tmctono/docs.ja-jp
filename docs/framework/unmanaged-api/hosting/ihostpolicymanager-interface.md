---
title: IHostPolicyManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503940"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="57e76-102">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57e76-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="57e76-103">中止、タイムアウト、またはエラーが発生した場合に共通言語ランタイム (CLR) が実行するアクションをホストに通知するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="57e76-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57e76-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="57e76-104">Methods</span></span>  
  
|<span data-ttu-id="57e76-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="57e76-105">Method</span></span>|<span data-ttu-id="57e76-106">説明</span><span class="sxs-lookup"><span data-stu-id="57e76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57e76-107">OnDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="57e76-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="57e76-108">CLR が、スレッドの中止またはアンロードに応答して[ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md)の呼び出しによって指定された既定のアクションを実行しようとしていることをホストに通知し <xref:System.AppDomain> ます。</span><span class="sxs-lookup"><span data-stu-id="57e76-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="57e76-109">OnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="57e76-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="57e76-110">リソース割り当てまたは再利用エラーに応答して、CLR が[ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)の呼び出しによって指定されたアクションを実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="57e76-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="57e76-111">OnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="57e76-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="57e76-112">タイムアウトに応答して[ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)への呼び出しによって指定されたアクションを CLR が実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="57e76-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57e76-113">要件</span><span class="sxs-lookup"><span data-stu-id="57e76-113">Requirements</span></span>  
 <span data-ttu-id="57e76-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e76-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57e76-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="57e76-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57e76-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="57e76-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57e76-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57e76-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57e76-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="57e76-118">See also</span></span>

- [<span data-ttu-id="57e76-119">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="57e76-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="57e76-120">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="57e76-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="57e76-121">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="57e76-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="57e76-122">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57e76-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="57e76-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57e76-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
