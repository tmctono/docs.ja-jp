---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55f3bd89f0ca177bcd4edef2e17a7d2256a0042a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773494"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="9dd09-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference メソッド</span><span class="sxs-lookup"><span data-stu-id="9dd09-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="9dd09-103">取得、 [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)指定した id の種類を持つアセンブリによって参照されるアセンブリ id の列挙子。</span><span class="sxs-lookup"><span data-stu-id="9dd09-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd09-104">構文</span><span class="sxs-lookup"><span data-stu-id="9dd09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dd09-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9dd09-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="9dd09-106">[in]WinNT.h で定義されているプロセッサのアーキテクチャを指定する有効な値。</span><span class="sxs-lookup"><span data-stu-id="9dd09-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9dd09-107">[in]将来の機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="9dd09-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="9dd09-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンをサポートする唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="9dd09-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="9dd09-109">[in]通常の呼び出しから返される、不透明なアセンブリ バインド id、 [iclrassemblyidentitymanager::getbindingidentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)または[iclrassemblyidentitymanager::getbindingidentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="9dd09-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="9dd09-110">[out]インターフェイス ポインターを`ICLRProbingAssemblyEnum`で識別されるアセンブリによって参照されるアセンブリへの参照を含む列挙子`pwzReferenceIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="9dd09-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dd09-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="9dd09-111">Return Value</span></span>  
  
|<span data-ttu-id="9dd09-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dd09-112">HRESULT</span></span>|<span data-ttu-id="9dd09-113">説明</span><span class="sxs-lookup"><span data-stu-id="9dd09-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dd09-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dd09-114">S_OK</span></span>|<span data-ttu-id="9dd09-115">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9dd09-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="9dd09-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dd09-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dd09-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9dd09-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dd09-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dd09-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dd09-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9dd09-119">The call timed out.</span></span>|  
|<span data-ttu-id="9dd09-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dd09-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dd09-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9dd09-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dd09-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dd09-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dd09-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9dd09-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dd09-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dd09-124">E_FAIL</span></span>|<span data-ttu-id="9dd09-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9dd09-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dd09-126">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9dd09-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dd09-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9dd09-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9dd09-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="9dd09-128">Requirements</span></span>  
 <span data-ttu-id="9dd09-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd09-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd09-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9dd09-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dd09-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9dd09-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dd09-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dd09-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd09-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dd09-133">See also</span></span>

- [<span data-ttu-id="9dd09-134">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9dd09-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9dd09-135">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9dd09-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9dd09-136">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9dd09-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
