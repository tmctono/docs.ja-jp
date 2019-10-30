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
ms.openlocfilehash: f4c200ad23ff7a71298e84fda857912da53978a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126690"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="e1068-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="e1068-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="e1068-103">指定したストリーム内のアセンブリによって参照されるアセンブリのアセンブリ id データを格納する[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e1068-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1068-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1068-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1068-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1068-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="e1068-106">から評価されるアセンブリを含む `IStream` へのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="e1068-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e1068-107">から将来の拡張のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="e1068-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="e1068-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンでサポートされている唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="e1068-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="e1068-109">から`ppReferenceEnum`から除外されるアセンブリのアセンブリ id データを格納する[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e1068-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="e1068-110">入出力`pExcludeAssembliesList`内のアセンブリを除く `pStream`内のアセンブリによって参照されるアセンブリのアセンブリ id データを格納する `ICLRReferenceAssemblyEnum` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e1068-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1068-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e1068-111">Return Value</span></span>  
  
|<span data-ttu-id="e1068-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1068-112">HRESULT</span></span>|<span data-ttu-id="e1068-113">説明</span><span class="sxs-lookup"><span data-stu-id="e1068-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1068-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1068-114">S_OK</span></span>|<span data-ttu-id="e1068-115">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e1068-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="e1068-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1068-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1068-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e1068-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1068-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1068-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1068-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e1068-119">The call timed out.</span></span>|  
|<span data-ttu-id="e1068-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1068-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1068-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e1068-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1068-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1068-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1068-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e1068-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1068-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1068-124">E_FAIL</span></span>|<span data-ttu-id="e1068-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e1068-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1068-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1068-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1068-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e1068-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1068-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1068-128">Remarks</span></span>  
 <span data-ttu-id="e1068-129">呼び出し元は、返された一覧から一連の既知のアセンブリ参照を除外することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1068-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="e1068-130">このセットは `pExcludeAssembliesList`によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="e1068-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1068-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="e1068-131">Requirements</span></span>  
 <span data-ttu-id="e1068-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1068-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1068-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1068-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1068-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e1068-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1068-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1068-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1068-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1068-136">See also</span></span>

- [<span data-ttu-id="e1068-137">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1068-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e1068-138">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1068-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e1068-139">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1068-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
