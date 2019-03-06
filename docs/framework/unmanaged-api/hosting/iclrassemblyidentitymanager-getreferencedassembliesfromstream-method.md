---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49fc3cf6aff94b5914040fba77acd0769fc73a43
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490035"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="77726-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="77726-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="77726-103">ポインターを取得、 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)指定されたストリーム内のアセンブリによって参照されるアセンブリのアセンブリの id データを格納しているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="77726-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77726-104">構文</span><span class="sxs-lookup"><span data-stu-id="77726-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77726-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77726-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="77726-106">[in]インターフェイス ポインターを`IStream`評価されるようにアセンブリを格納しています。</span><span class="sxs-lookup"><span data-stu-id="77726-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="77726-107">[in]将来の機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="77726-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="77726-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンをサポートする唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="77726-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="77726-109">[in]ポインター、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)から除外するアセンブリのアセンブリの id データを格納しているオブジェクト`ppReferenceEnum`します。</span><span class="sxs-lookup"><span data-stu-id="77726-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="77726-110">[out]アドレスへのポインター、`ICLRReferenceAssemblyEnum`内のアセンブリによって参照されるアセンブリのアセンブリの id データを格納しているオブジェクト`pStream`、内のアセンブリを除く`pExcludeAssembliesList`します。</span><span class="sxs-lookup"><span data-stu-id="77726-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77726-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="77726-111">Return Value</span></span>  
  
|<span data-ttu-id="77726-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77726-112">HRESULT</span></span>|<span data-ttu-id="77726-113">説明</span><span class="sxs-lookup"><span data-stu-id="77726-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77726-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="77726-114">S_OK</span></span>|<span data-ttu-id="77726-115">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="77726-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="77726-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77726-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77726-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="77726-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77726-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77726-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77726-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="77726-119">The call timed out.</span></span>|  
|<span data-ttu-id="77726-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77726-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77726-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="77726-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77726-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77726-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77726-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="77726-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77726-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77726-124">E_FAIL</span></span>|<span data-ttu-id="77726-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="77726-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77726-126">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="77726-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77726-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="77726-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77726-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="77726-128">Remarks</span></span>  
 <span data-ttu-id="77726-129">返された一覧から既知のアセンブリ参照のセットを除外する、呼び出し元を選択できます。</span><span class="sxs-lookup"><span data-stu-id="77726-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="77726-130">このセットがによって定義されている`pExcludeAssembliesList`します。</span><span class="sxs-lookup"><span data-stu-id="77726-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77726-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="77726-131">Requirements</span></span>  
 <span data-ttu-id="77726-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77726-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77726-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77726-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77726-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="77726-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77726-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77726-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77726-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="77726-136">See also</span></span>
- [<span data-ttu-id="77726-137">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77726-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="77726-138">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77726-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="77726-139">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77726-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
