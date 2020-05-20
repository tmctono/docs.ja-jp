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
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703479"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="6b1f0-102">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b1f0-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="6b1f0-103">エラーやタイムアウトが発生した場合に実行されるポリシーアクションをホストが指定できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b1f0-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-104">Methods</span></span>  
  
|<span data-ttu-id="6b1f0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-105">Method</span></span>|<span data-ttu-id="6b1f0-106">説明</span><span class="sxs-lookup"><span data-stu-id="6b1f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b1f0-107">SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="6b1f0-108">指定したエラーが発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="6b1f0-109">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="6b1f0-110">指定された操作がタイムアウトしたときに CLR が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="6b1f0-111">SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="6b1f0-112">指定された操作が発生したときに CLR が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="6b1f0-113">SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="6b1f0-114">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="6b1f0-115">SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="6b1f0-116">指定された操作のタイムアウト値を設定し、操作が発生したときに CLR が実行する必要があるポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="6b1f0-117">SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="6b1f0-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="6b1f0-118">未処理の例外が発生した場合の CLR の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b1f0-119">要件</span><span class="sxs-lookup"><span data-stu-id="6b1f0-119">Requirements</span></span>  
 <span data-ttu-id="6b1f0-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b1f0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b1f0-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6b1f0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b1f0-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6b1f0-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b1f0-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b1f0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1f0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b1f0-124">See also</span></span>

- [<span data-ttu-id="6b1f0-125">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="6b1f0-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="6b1f0-126">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="6b1f0-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="6b1f0-127">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="6b1f0-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="6b1f0-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b1f0-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
