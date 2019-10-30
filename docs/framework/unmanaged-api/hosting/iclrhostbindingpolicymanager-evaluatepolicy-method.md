---
title: ICLRHostBindingPolicyManager::EvaluatePolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141184"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="7cc33-102">ICLRHostBindingPolicyManager::EvaluatePolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="7cc33-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="7cc33-103">ホストの代わりにバインドポリシーを評価します。</span><span class="sxs-lookup"><span data-stu-id="7cc33-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc33-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cc33-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cc33-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cc33-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="7cc33-106">からポリシー評価の前のアセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7cc33-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="7cc33-107">からポリシーデータを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7cc33-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="7cc33-108">から`pbApplicationPolicy` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="7cc33-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="7cc33-109">入出力新しいポリシーデータを評価した後のアセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7cc33-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="7cc33-110">[入力、出力]新しいポリシーデータを評価した後のアセンブリ id 参照バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7cc33-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="7cc33-111">入出力適用されているポリシーを示す[Ebindpolicylevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)値の論理和の組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7cc33-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cc33-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="7cc33-112">Return Value</span></span>  
  
|<span data-ttu-id="7cc33-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cc33-113">HRESULT</span></span>|<span data-ttu-id="7cc33-114">説明</span><span class="sxs-lookup"><span data-stu-id="7cc33-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cc33-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cc33-115">S_OK</span></span>|<span data-ttu-id="7cc33-116">評価が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7cc33-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="7cc33-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7cc33-117">E_INVALIDARG</span></span>|<span data-ttu-id="7cc33-118">`pwzReferenceIdentity` または `pbApplicationPolicy` のいずれかが null 参照です。</span><span class="sxs-lookup"><span data-stu-id="7cc33-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="7cc33-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7cc33-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7cc33-120">`cbAppPolicySize` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="7cc33-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="7cc33-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cc33-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cc33-122">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7cc33-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cc33-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cc33-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cc33-124">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7cc33-124">The call timed out.</span></span>|  
|<span data-ttu-id="7cc33-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cc33-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cc33-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7cc33-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cc33-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cc33-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cc33-128">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7cc33-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cc33-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cc33-129">E_FAIL</span></span>|<span data-ttu-id="7cc33-130">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7cc33-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cc33-131">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7cc33-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cc33-132">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7cc33-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cc33-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cc33-133">Remarks</span></span>  
 <span data-ttu-id="7cc33-134">`EvaluatePolicy` メソッドを使用すると、ホストは、ホスト固有のアセンブリのバージョン管理要件を維持するために、バインドポリシーに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="7cc33-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="7cc33-135">ポリシーエンジン自体は CLR 内に残ります。</span><span class="sxs-lookup"><span data-stu-id="7cc33-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc33-136">［要件］</span><span class="sxs-lookup"><span data-stu-id="7cc33-136">Requirements</span></span>  
 <span data-ttu-id="7cc33-137">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cc33-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc33-138">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7cc33-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cc33-139">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7cc33-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cc33-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc33-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc33-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cc33-141">See also</span></span>

- [<span data-ttu-id="7cc33-142">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cc33-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
