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
ms.openlocfilehash: 65dc330e88cb2457cc34f9994313373ab1ab84aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126702"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="ee1c5-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="ee1c5-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="ee1c5-103">指定したファイルパスにあるアセンブリによって参照されるアセンブリのリストを含む[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee1c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee1c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee1c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee1c5-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="ee1c5-106">から評価されるアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ee1c5-107">から将来の拡張のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="ee1c5-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンでサポートされている唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="ee1c5-109">から`ppReferenceEnum`から除外するアセンブリを表す[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="ee1c5-110">入出力`pwzFilePath`にあるアセンブリによって参照されるアセンブリのアセンブリ id データを格納する `ICLRReferenceAssemblyEnum` オブジェクトのアドレスへのポインター。 `pExcludeAssembliesList`によって表されるアセンブリは除外されます。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee1c5-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="ee1c5-111">Return Value</span></span>  
  
|<span data-ttu-id="ee1c5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee1c5-112">HRESULT</span></span>|<span data-ttu-id="ee1c5-113">説明</span><span class="sxs-lookup"><span data-stu-id="ee1c5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee1c5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee1c5-114">S_OK</span></span>|<span data-ttu-id="ee1c5-115">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="ee1c5-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee1c5-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee1c5-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ee1c5-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee1c5-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ee1c5-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-119">The call timed out.</span></span>|  
|<span data-ttu-id="ee1c5-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee1c5-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ee1c5-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ee1c5-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ee1c5-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ee1c5-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ee1c5-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee1c5-124">E_FAIL</span></span>|<span data-ttu-id="ee1c5-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee1c5-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ee1c5-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee1c5-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee1c5-128">Remarks</span></span>  
 <span data-ttu-id="ee1c5-129">呼び出し元は、返された一覧から一連の既知のアセンブリ参照を除外することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="ee1c5-130">このセットは `pExcludeAssembliesList` パラメーターによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee1c5-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="ee1c5-131">Requirements</span></span>  
 <span data-ttu-id="ee1c5-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee1c5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1c5-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ee1c5-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee1c5-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ee1c5-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee1c5-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1c5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1c5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee1c5-136">See also</span></span>

- [<span data-ttu-id="ee1c5-137">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee1c5-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ee1c5-138">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee1c5-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ee1c5-139">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee1c5-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
