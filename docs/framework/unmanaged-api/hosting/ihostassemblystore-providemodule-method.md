---
title: IHostAssemblyStore::ProvideModule メソッド
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124473"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="8606c-102">IHostAssemblyStore::ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="8606c-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="8606c-103">アセンブリ内のモジュール、またはリンクされている (埋め込みではない) リソースファイル内のモジュールを解決します。</span><span class="sxs-lookup"><span data-stu-id="8606c-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8606c-104">構文</span><span class="sxs-lookup"><span data-stu-id="8606c-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8606c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8606c-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="8606c-106">から要求されたモジュールの <xref:System.AppDomain>、アセンブリ、およびモジュール名を記述する[Modulebindinfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8606c-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="8606c-107">入出力読み込まれたモジュールを含む `IStream` の一意の識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8606c-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="8606c-108">入出力読み込むポータブル実行可能 (PE) イメージを格納する `IStream` オブジェクトのアドレスへのポインター。モジュールが見つからなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="8606c-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="8606c-109">入出力要求されたモジュールのプログラムデバッグ (PDB) 情報を格納している `IStream` オブジェクトのアドレスへのポインター。 .pdb ファイルが見つからなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="8606c-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8606c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="8606c-110">Return Value</span></span>  
  
|<span data-ttu-id="8606c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8606c-111">HRESULT</span></span>|<span data-ttu-id="8606c-112">説明</span><span class="sxs-lookup"><span data-stu-id="8606c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8606c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8606c-113">S_OK</span></span>|<span data-ttu-id="8606c-114">`ProvideModule` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8606c-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="8606c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8606c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8606c-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="8606c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8606c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8606c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8606c-118">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8606c-118">The call timed out.</span></span>|  
|<span data-ttu-id="8606c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8606c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8606c-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8606c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8606c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8606c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8606c-122">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="8606c-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8606c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8606c-123">E_FAIL</span></span>|<span data-ttu-id="8606c-124">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8606c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8606c-125">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8606c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8606c-126">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8606c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8606c-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="8606c-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="8606c-128">要求されたアセンブリまたはリンクされたリソースが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8606c-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="8606c-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8606c-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8606c-130">`pdwModuleId` は、ホストが返す識別子を格納するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="8606c-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8606c-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="8606c-131">Remarks</span></span>  
 <span data-ttu-id="8606c-132">`pdwModuleId` に対して返される id 値は、ホストによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="8606c-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="8606c-133">識別子は、プロセスの有効期間内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8606c-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="8606c-134">CLR は、この値を、関連付けられているストリームの一意の識別子として使用します。</span><span class="sxs-lookup"><span data-stu-id="8606c-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="8606c-135">各値は、[アセンブリ](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)の呼び出しによって返される `pAssemblyId` の値と、`ProvideModule`の他の呼び出しによって返される `pdwModuleId` の値とを比較して確認されます。</span><span class="sxs-lookup"><span data-stu-id="8606c-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="8606c-136">ホストが別の `IStream`に対して同じ識別子の値を返した場合、CLR は、そのストリームの内容が既にマップされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8606c-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="8606c-137">その場合、CLR は新しいイメージをマップするのではなく、イメージの既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8606c-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="8606c-138">したがって、識別子は `ProvideAssembly`から返されたアセンブリ識別子と重複することはできません。</span><span class="sxs-lookup"><span data-stu-id="8606c-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8606c-139">［要件］</span><span class="sxs-lookup"><span data-stu-id="8606c-139">Requirements</span></span>  
 <span data-ttu-id="8606c-140">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8606c-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8606c-141">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8606c-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8606c-142">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8606c-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8606c-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8606c-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8606c-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8606c-144">See also</span></span>

- [<span data-ttu-id="8606c-145">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8606c-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8606c-146">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8606c-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="8606c-147">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8606c-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
