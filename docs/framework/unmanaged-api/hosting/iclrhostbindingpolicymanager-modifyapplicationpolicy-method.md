---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178103"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="4c183-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="4c183-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="4c183-103">指定したアセンブリのバインディング ポリシーを変更し、新しいバージョンのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c183-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c183-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c183-104">Syntax</span></span>  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c183-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c183-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="4c183-106">[in]変更するアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="4c183-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="4c183-107">[in]変更されたアセンブリの新しい ID。</span><span class="sxs-lookup"><span data-stu-id="4c183-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="4c183-108">[in]変更するアセンブリのバインディング ポリシー データを格納するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c183-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="4c183-109">[in]置き換えるバインディング ポリシーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="4c183-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="4c183-110">[in]リダイレクトの制御[を](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)示す値の論理 OR の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="4c183-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="4c183-111">[アウト]新しいバインディング ポリシー データを格納するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c183-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="4c183-112">[イン、アウト]新しいバインディング ポリシー バッファのサイズへのポインタ。</span><span class="sxs-lookup"><span data-stu-id="4c183-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c183-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="4c183-113">Return Value</span></span>  
  
|<span data-ttu-id="4c183-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c183-114">HRESULT</span></span>|<span data-ttu-id="4c183-115">説明</span><span class="sxs-lookup"><span data-stu-id="4c183-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c183-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c183-116">S_OK</span></span>|<span data-ttu-id="4c183-117">ポリシーは正常に変更されました。</span><span class="sxs-lookup"><span data-stu-id="4c183-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="4c183-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4c183-118">E_INVALIDARG</span></span>|<span data-ttu-id="4c183-119">`pwzSourceAssemblyIdentity`または`pwzTargetAssemblyIdentity`null 参照です。</span><span class="sxs-lookup"><span data-stu-id="4c183-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="4c183-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4c183-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4c183-121">`pbNewApplicationPolicy` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="4c183-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="4c183-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4c183-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4c183-123">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="4c183-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4c183-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4c183-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4c183-125">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4c183-125">The call timed out.</span></span>|  
|<span data-ttu-id="4c183-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c183-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4c183-127">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4c183-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4c183-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4c183-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4c183-129">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="4c183-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4c183-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4c183-130">E_FAIL</span></span>|<span data-ttu-id="4c183-131">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4c183-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4c183-132">メソッドがE_FAILを返した後、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c183-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4c183-133">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="4c183-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c183-134">解説</span><span class="sxs-lookup"><span data-stu-id="4c183-134">Remarks</span></span>  
 <span data-ttu-id="4c183-135">この`ModifyApplicationPolicy`メソッドは 2 回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4c183-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="4c183-136">最初の呼び出しでは、パラメーターに`pbNewApplicationPolicy`null 値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c183-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="4c183-137">この呼び出しは、 に`pcbNewAppPolicySize`必要な値を返します。</span><span class="sxs-lookup"><span data-stu-id="4c183-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="4c183-138">2 番目の呼び出し`pcbNewAppPolicySize`では、この値を に指定し、`pbNewApplicationPolicy`そのサイズの バッファーを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c183-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c183-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c183-139">Requirements</span></span>  
 <span data-ttu-id="4c183-140">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c183-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c183-141">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c183-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c183-142">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="4c183-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c183-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c183-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c183-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c183-144">See also</span></span>

- [<span data-ttu-id="4c183-145">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c183-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
