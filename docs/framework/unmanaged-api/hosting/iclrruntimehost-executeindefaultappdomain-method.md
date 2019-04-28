---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e6805dc67f7ec5ceb8c67d77462a0200b6c0317
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641425"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="55a8b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="55a8b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="55a8b-103">指定されたマネージ アセンブリで指定した型の指定したメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="55a8b-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a8b-104">構文</span><span class="sxs-lookup"><span data-stu-id="55a8b-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55a8b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55a8b-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="55a8b-106">[in]パス、<xref:System.Reflection.Assembly>を定義する、<xref:System.Type>メソッドが呼び出されるです。</span><span class="sxs-lookup"><span data-stu-id="55a8b-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="55a8b-107">[in]名前、<xref:System.Type>に呼び出すメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="55a8b-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="55a8b-108">[in]呼び出すメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="55a8b-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="55a8b-109">[in]メソッドに渡す文字列パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="55a8b-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="55a8b-110">[out]呼び出されたメソッドで返される整数値。</span><span class="sxs-lookup"><span data-stu-id="55a8b-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55a8b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="55a8b-111">Return Value</span></span>  
  
|<span data-ttu-id="55a8b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55a8b-112">HRESULT</span></span>|<span data-ttu-id="55a8b-113">説明</span><span class="sxs-lookup"><span data-stu-id="55a8b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55a8b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="55a8b-114">S_OK</span></span>|<span data-ttu-id="55a8b-115">`ExecuteInDefaultAppDomain` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="55a8b-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="55a8b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55a8b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55a8b-117">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="55a8b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55a8b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55a8b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55a8b-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="55a8b-119">The call timed out.</span></span>|  
|<span data-ttu-id="55a8b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55a8b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55a8b-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="55a8b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55a8b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55a8b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55a8b-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="55a8b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55a8b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55a8b-124">E_FAIL</span></span>|<span data-ttu-id="55a8b-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="55a8b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55a8b-126">メソッドから E_FAIL が返された場合、CRL は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="55a8b-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="55a8b-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="55a8b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55a8b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="55a8b-128">Remarks</span></span>  
 <span data-ttu-id="55a8b-129">呼び出されたメソッドには、次のシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="55a8b-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="55a8b-130">場所`pwzMethodName`呼び出されたメソッドの名前を表すと`pwzArgument`文字列値がそのメソッドに渡すパラメーターとして表します。</span><span class="sxs-lookup"><span data-stu-id="55a8b-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="55a8b-131">、S_ok HRESULT 値が設定されている場合`pReturnValue`が呼び出されたメソッドで返される整数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="55a8b-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="55a8b-132">それ以外の場合、`pReturnValue`が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="55a8b-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a8b-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="55a8b-133">Requirements</span></span>  
 <span data-ttu-id="55a8b-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55a8b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a8b-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55a8b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55a8b-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="55a8b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55a8b-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a8b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a8b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="55a8b-138">See also</span></span>

- [<span data-ttu-id="55a8b-139">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55a8b-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
