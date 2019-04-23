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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07a4998f86958e21fffc8ba8657ec9f2a170f43e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112438"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="f30f0-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="f30f0-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="f30f0-103">指定されたアセンブリのバインディング ポリシーを変更し、新しいバージョンのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f30f0-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f30f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="f30f0-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="f30f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f30f0-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="f30f0-106">[in]変更するアセンブリの id。</span><span class="sxs-lookup"><span data-stu-id="f30f0-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="f30f0-107">[in]変更されたアセンブリの新しい id。</span><span class="sxs-lookup"><span data-stu-id="f30f0-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="f30f0-108">[in]変更するアセンブリのバインド ポリシー データを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f30f0-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="f30f0-109">[in]置き換えられるバインディング ポリシーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="f30f0-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="f30f0-110">[in]論理 OR の組み合わせの[EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)リダイレクトのコントロールを示す値。</span><span class="sxs-lookup"><span data-stu-id="f30f0-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="f30f0-111">[out]新しいバインド ポリシー データを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f30f0-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="f30f0-112">[入力、出力]新しいバインディング ポリシー バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f30f0-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f30f0-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="f30f0-113">Return Value</span></span>  
  
|<span data-ttu-id="f30f0-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f30f0-114">HRESULT</span></span>|<span data-ttu-id="f30f0-115">説明</span><span class="sxs-lookup"><span data-stu-id="f30f0-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f30f0-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f30f0-116">S_OK</span></span>|<span data-ttu-id="f30f0-117">ポリシーが正常に変更します。</span><span class="sxs-lookup"><span data-stu-id="f30f0-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="f30f0-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f30f0-118">E_INVALIDARG</span></span>|<span data-ttu-id="f30f0-119">`pwzSourceAssemblyIdentity` または`pwzTargetAssemblyIdentity`が null 参照。</span><span class="sxs-lookup"><span data-stu-id="f30f0-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="f30f0-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f30f0-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f30f0-121">`pbNewApplicationPolicy` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="f30f0-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="f30f0-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f30f0-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f30f0-123">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="f30f0-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f30f0-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f30f0-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f30f0-125">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="f30f0-125">The call timed out.</span></span>|  
|<span data-ttu-id="f30f0-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f30f0-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f30f0-127">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f30f0-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f30f0-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f30f0-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f30f0-129">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="f30f0-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f30f0-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f30f0-130">E_FAIL</span></span>|<span data-ttu-id="f30f0-131">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f30f0-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f30f0-132">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f30f0-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f30f0-133">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f30f0-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f30f0-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="f30f0-134">Remarks</span></span>  
 <span data-ttu-id="f30f0-135">`ModifyApplicationPolicy`メソッドを 2 回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f30f0-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="f30f0-136">最初の呼び出しは、null 値を指定する必要があります、`pbNewApplicationPolicy`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f30f0-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="f30f0-137">この呼び出しのために必要な値が返さ`pcbNewAppPolicySize`します。</span><span class="sxs-lookup"><span data-stu-id="f30f0-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="f30f0-138">2 番目の呼び出しがこの値を指定する必要があります`pcbNewAppPolicySize`、そのサイズのバッファーを指すと`pbNewApplicationPolicy`します。</span><span class="sxs-lookup"><span data-stu-id="f30f0-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f30f0-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="f30f0-139">Requirements</span></span>  
 <span data-ttu-id="f30f0-140">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f30f0-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f30f0-141">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f30f0-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f30f0-142">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f30f0-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f30f0-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f30f0-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30f0-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f30f0-144">See also</span></span>

- [<span data-ttu-id="f30f0-145">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f30f0-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
