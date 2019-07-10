---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb7500c1c9d09cffd0c1f3365b2a7cf939f78531
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773420"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="a00fa-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="a00fa-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="a00fa-103">取得、 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)インスタンスを指定したファイル パスにあるアセンブリによって参照されるアセンブリの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a00fa-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="a00fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a00fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a00fa-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a00fa-106">[in]評価するアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="a00fa-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a00fa-107">[in]将来の機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="a00fa-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="a00fa-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンをサポートする唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="a00fa-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="a00fa-109">[in]ポインター、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)から除外するアセンブリを表すオブジェクトを`ppReferenceEnum`します。</span><span class="sxs-lookup"><span data-stu-id="a00fa-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="a00fa-110">[out]アドレスへのポインター、`ICLRReferenceAssemblyEnum`でアセンブリによって参照されるアセンブリのアセンブリの id データを格納しているオブジェクト`pwzFilePath`、によって表されるアセンブリを除く`pExcludeAssembliesList`します。</span><span class="sxs-lookup"><span data-stu-id="a00fa-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a00fa-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="a00fa-111">Return Value</span></span>  
  
|<span data-ttu-id="a00fa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a00fa-112">HRESULT</span></span>|<span data-ttu-id="a00fa-113">説明</span><span class="sxs-lookup"><span data-stu-id="a00fa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a00fa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a00fa-114">S_OK</span></span>|<span data-ttu-id="a00fa-115">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="a00fa-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="a00fa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a00fa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a00fa-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="a00fa-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a00fa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a00fa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a00fa-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="a00fa-119">The call timed out.</span></span>|  
|<span data-ttu-id="a00fa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a00fa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a00fa-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a00fa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a00fa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a00fa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a00fa-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="a00fa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a00fa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a00fa-124">E_FAIL</span></span>|<span data-ttu-id="a00fa-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a00fa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a00fa-126">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a00fa-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a00fa-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a00fa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a00fa-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="a00fa-128">Remarks</span></span>  
 <span data-ttu-id="a00fa-129">返された一覧から既知のアセンブリ参照のセットを除外する、呼び出し元を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a00fa-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="a00fa-130">このセットは、`pExcludeAssembliesList`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a00fa-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00fa-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="a00fa-131">Requirements</span></span>  
 <span data-ttu-id="a00fa-132">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a00fa-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00fa-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a00fa-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a00fa-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a00fa-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a00fa-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00fa-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00fa-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a00fa-136">See also</span></span>

- [<span data-ttu-id="a00fa-137">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a00fa-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a00fa-138">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a00fa-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a00fa-139">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a00fa-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
