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
ms.openlocfilehash: 3c4f673d88594e86004c6d51a4d58a0ac4642875
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615944"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="a47d0-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="a47d0-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="a47d0-103">指定したファイルパスにあるアセンブリによって参照されるアセンブリのリストを含む[ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a47d0-103">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a47d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a47d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a47d0-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a47d0-106">から評価されるアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="a47d0-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a47d0-107">から将来の拡張のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="a47d0-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="a47d0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンでサポートされている唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="a47d0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="a47d0-109">からから除外するアセンブリを表す[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)オブジェクトへのポインター `ppReferenceEnum` 。</span><span class="sxs-lookup"><span data-stu-id="a47d0-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="a47d0-110">入出力によって表されるアセンブリを `ICLRReferenceAssemblyEnum` 除く、アセンブリによって参照されるアセンブリのアセンブリ id データを格納するオブジェクトのアドレスへのポインター `pwzFilePath` `pExcludeAssembliesList` 。</span><span class="sxs-lookup"><span data-stu-id="a47d0-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a47d0-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="a47d0-111">Return Value</span></span>  
  
|<span data-ttu-id="a47d0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a47d0-112">HRESULT</span></span>|<span data-ttu-id="a47d0-113">説明</span><span class="sxs-lookup"><span data-stu-id="a47d0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a47d0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a47d0-114">S_OK</span></span>|<span data-ttu-id="a47d0-115">メソッドから正常に値が返されました。</span><span class="sxs-lookup"><span data-stu-id="a47d0-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="a47d0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a47d0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a47d0-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a47d0-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a47d0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a47d0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a47d0-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a47d0-119">The call timed out.</span></span>|  
|<span data-ttu-id="a47d0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a47d0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a47d0-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a47d0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a47d0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a47d0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a47d0-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="a47d0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a47d0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a47d0-124">E_FAIL</span></span>|<span data-ttu-id="a47d0-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a47d0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a47d0-126">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a47d0-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a47d0-127">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a47d0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a47d0-128">解説</span><span class="sxs-lookup"><span data-stu-id="a47d0-128">Remarks</span></span>  
 <span data-ttu-id="a47d0-129">呼び出し元は、返された一覧から一連の既知のアセンブリ参照を除外することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a47d0-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="a47d0-130">このセットは、パラメーターによって定義され `pExcludeAssembliesList` ます。</span><span class="sxs-lookup"><span data-stu-id="a47d0-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47d0-131">要件</span><span class="sxs-lookup"><span data-stu-id="a47d0-131">Requirements</span></span>  
 <span data-ttu-id="a47d0-132">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47d0-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47d0-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a47d0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a47d0-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a47d0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a47d0-135">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47d0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47d0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a47d0-136">See also</span></span>

- [<span data-ttu-id="a47d0-137">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a47d0-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a47d0-138">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a47d0-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a47d0-139">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a47d0-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
