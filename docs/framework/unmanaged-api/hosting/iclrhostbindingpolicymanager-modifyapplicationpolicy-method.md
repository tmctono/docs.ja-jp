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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141080"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="3d588-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="3d588-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="3d588-103">指定したアセンブリのバインディングポリシーを変更し、新しいバージョンのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d588-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d588-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d588-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3d588-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d588-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="3d588-106">から変更するアセンブリの id。</span><span class="sxs-lookup"><span data-stu-id="3d588-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="3d588-107">から変更されたアセンブリの新しい id。</span><span class="sxs-lookup"><span data-stu-id="3d588-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="3d588-108">から変更するアセンブリのバインディングポリシーデータを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d588-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="3d588-109">から置換されるバインディングポリシーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="3d588-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="3d588-110">からリダイレクトの制御を示す[Ehostbindingpolicymodifyflags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)値の論理的または組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="3d588-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="3d588-111">入出力新しいバインドポリシーデータを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d588-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="3d588-112">[入力、出力]新しいバインドポリシーバッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d588-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d588-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="3d588-113">Return Value</span></span>  
  
|<span data-ttu-id="3d588-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d588-114">HRESULT</span></span>|<span data-ttu-id="3d588-115">説明</span><span class="sxs-lookup"><span data-stu-id="3d588-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d588-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d588-116">S_OK</span></span>|<span data-ttu-id="3d588-117">ポリシーが正常に変更されました。</span><span class="sxs-lookup"><span data-stu-id="3d588-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="3d588-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3d588-118">E_INVALIDARG</span></span>|<span data-ttu-id="3d588-119">`pwzSourceAssemblyIdentity` または `pwzTargetAssemblyIdentity` が null 参照でした。</span><span class="sxs-lookup"><span data-stu-id="3d588-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="3d588-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3d588-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3d588-121">`pbNewApplicationPolicy` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="3d588-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="3d588-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d588-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d588-123">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3d588-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d588-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d588-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d588-125">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3d588-125">The call timed out.</span></span>|  
|<span data-ttu-id="3d588-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d588-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d588-127">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3d588-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d588-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d588-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d588-129">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3d588-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d588-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d588-130">E_FAIL</span></span>|<span data-ttu-id="3d588-131">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3d588-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d588-132">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3d588-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d588-133">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3d588-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d588-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d588-134">Remarks</span></span>  
 <span data-ttu-id="3d588-135">`ModifyApplicationPolicy` メソッドは、2回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3d588-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="3d588-136">最初の呼び出しでは、`pbNewApplicationPolicy` パラメーターに null 値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d588-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="3d588-137">この呼び出しは、`pcbNewAppPolicySize`に必要な値と共に返されます。</span><span class="sxs-lookup"><span data-stu-id="3d588-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="3d588-138">2番目の呼び出しでは、`pcbNewAppPolicySize`にこの値を指定し、`pbNewApplicationPolicy`のバッファーのサイズをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d588-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d588-139">［要件］</span><span class="sxs-lookup"><span data-stu-id="3d588-139">Requirements</span></span>  
 <span data-ttu-id="3d588-140">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d588-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d588-141">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3d588-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d588-142">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3d588-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d588-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d588-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d588-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d588-144">See also</span></span>

- [<span data-ttu-id="3d588-145">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d588-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
