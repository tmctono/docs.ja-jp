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
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176410"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="63b7e-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="63b7e-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="63b7e-103">指定したマネージ アセンブリ内の指定した型の指定したメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="63b7e-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b7e-104">構文</span><span class="sxs-lookup"><span data-stu-id="63b7e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63b7e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63b7e-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="63b7e-106">[in]呼び出される<xref:System.Reflection.Assembly>メソッドを<xref:System.Type>定義する へのパス。</span><span class="sxs-lookup"><span data-stu-id="63b7e-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="63b7e-107">[in]呼び出す<xref:System.Type>メソッドを定義する の名前。</span><span class="sxs-lookup"><span data-stu-id="63b7e-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="63b7e-108">[in]呼び出すメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="63b7e-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="63b7e-109">[in]メソッドに渡す文字列パラメーター。</span><span class="sxs-lookup"><span data-stu-id="63b7e-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="63b7e-110">[アウト]呼び出されたメソッドによって返される整数値。</span><span class="sxs-lookup"><span data-stu-id="63b7e-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63b7e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="63b7e-111">Return Value</span></span>  
  
|<span data-ttu-id="63b7e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63b7e-112">HRESULT</span></span>|<span data-ttu-id="63b7e-113">説明</span><span class="sxs-lookup"><span data-stu-id="63b7e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63b7e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="63b7e-114">S_OK</span></span>|<span data-ttu-id="63b7e-115">`ExecuteInDefaultAppDomain`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="63b7e-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="63b7e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63b7e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63b7e-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="63b7e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63b7e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63b7e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63b7e-119">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="63b7e-119">The call timed out.</span></span>|  
|<span data-ttu-id="63b7e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63b7e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63b7e-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="63b7e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63b7e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63b7e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63b7e-123">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="63b7e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63b7e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63b7e-124">E_FAIL</span></span>|<span data-ttu-id="63b7e-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="63b7e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63b7e-126">メソッドがE_FAILを返す場合、プロセス内で CRL を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="63b7e-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="63b7e-127">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="63b7e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63b7e-128">解説</span><span class="sxs-lookup"><span data-stu-id="63b7e-128">Remarks</span></span>  
 <span data-ttu-id="63b7e-129">呼び出されるメソッドには、次のシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="63b7e-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="63b7e-130">呼`pwzMethodName`び出されたメソッドの名前を表し`pwzArgument`、そのメソッドにパラメーターとして渡される文字列値を表します。</span><span class="sxs-lookup"><span data-stu-id="63b7e-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="63b7e-131">HRESULT 値が S_OK に設定`pReturnValue`されている場合は、呼び出されたメソッドによって返される整数値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b7e-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="63b7e-132">それ以外`pReturnValue`の場合は、設定されません。</span><span class="sxs-lookup"><span data-stu-id="63b7e-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63b7e-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="63b7e-133">Requirements</span></span>  
 <span data-ttu-id="63b7e-134">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b7e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63b7e-135">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63b7e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63b7e-136">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="63b7e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63b7e-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b7e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b7e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="63b7e-138">See also</span></span>

- [<span data-ttu-id="63b7e-139">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63b7e-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
