---
title: IHostAssemblyStore::ProvideAssembly メソッド
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124484"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="7ac03-102">IHostAssemblyStore::ProvideAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="7ac03-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="7ac03-103">[IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)から返された[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)によって参照されていないアセンブリへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ac03-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="7ac03-104">共通言語ランタイム (CLR) は、一覧に表示されないアセンブリごとに `ProvideAssembly` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7ac03-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac03-105">構文</span><span class="sxs-lookup"><span data-stu-id="7ac03-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ac03-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ac03-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="7ac03-107">からホストが特定のバインド特性 (バージョン管理ポリシーの有無、バインド先のアセンブリなど) を決定するために使用する[Assemblybindinfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7ac03-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="7ac03-108">入出力この `IStream`の要求されたアセンブリの一意の識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7ac03-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="7ac03-109">入出力プラットフォーム呼び出しを必要とせずに、要求されたアセンブリの証拠を決定するために使用されるホスト固有のデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7ac03-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="7ac03-110">`pHostContext` は、マネージ <xref:System.Reflection.Assembly> クラスの <xref:System.Reflection.Assembly.HostContext%2A> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="7ac03-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="7ac03-111">入出力読み込むポータブル実行可能 (PE) イメージを含む `IStream` のアドレスへのポインター。アセンブリが見つからなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="7ac03-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="7ac03-112">入出力プログラムデバッグ (PDB) 情報を格納している `IStream` のアドレスへのポインター。 .pdb ファイルが見つからなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="7ac03-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ac03-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="7ac03-113">Return Value</span></span>  
  
|<span data-ttu-id="7ac03-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ac03-114">HRESULT</span></span>|<span data-ttu-id="7ac03-115">説明</span><span class="sxs-lookup"><span data-stu-id="7ac03-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ac03-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ac03-116">S_OK</span></span>|<span data-ttu-id="7ac03-117">`ProvideAssembly` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7ac03-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="7ac03-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ac03-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ac03-119">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7ac03-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ac03-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ac03-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ac03-121">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7ac03-121">The call timed out.</span></span>|  
|<span data-ttu-id="7ac03-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ac03-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ac03-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7ac03-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ac03-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ac03-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ac03-125">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7ac03-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ac03-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ac03-126">E_FAIL</span></span>|<span data-ttu-id="7ac03-127">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7ac03-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ac03-128">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7ac03-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ac03-129">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7ac03-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7ac03-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="7ac03-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="7ac03-131">要求されたアセンブリが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ac03-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="7ac03-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7ac03-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7ac03-133">`pAssemblyId` によって指定されたバッファーサイズが、ホストが返す識別子を保持するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="7ac03-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ac03-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ac03-134">Remarks</span></span>  
 <span data-ttu-id="7ac03-135">`pAssemblyId` に対して返される id 値は、ホストによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="7ac03-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="7ac03-136">識別子は、プロセスの有効期間内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac03-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="7ac03-137">CLR は、この値をストリームの一意の識別子として使用します。</span><span class="sxs-lookup"><span data-stu-id="7ac03-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="7ac03-138">また、`ProvideAssembly`の他の呼び出しによって返される `pAssemblyId` の値に対して各値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="7ac03-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="7ac03-139">ホストが別の `IStream`に対して同じ `pAssemblyId` 値を返した場合、CLR は、そのストリームの内容が既にマップされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ac03-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="7ac03-140">その場合、ランタイムは新しいイメージをマップするのではなく、イメージの既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7ac03-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac03-141">［要件］</span><span class="sxs-lookup"><span data-stu-id="7ac03-141">Requirements</span></span>  
 <span data-ttu-id="7ac03-142">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac03-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac03-143">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7ac03-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ac03-144">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7ac03-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ac03-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac03-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac03-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ac03-146">See also</span></span>

- [<span data-ttu-id="7ac03-147">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ac03-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7ac03-148">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ac03-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="7ac03-149">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ac03-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
