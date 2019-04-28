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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599349"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="adba8-102">IHostAssemblyStore::ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="adba8-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="adba8-103">アセンブリまたは、リンクされた (ただし、埋め込まれたされません) 内のモジュールのリソース ファイルを解決します。</span><span class="sxs-lookup"><span data-stu-id="adba8-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adba8-104">構文</span><span class="sxs-lookup"><span data-stu-id="adba8-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adba8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="adba8-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="adba8-106">[in]ポインターを[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 、要求されたモジュールを記述するインスタンス<xref:System.AppDomain>アセンブリとモジュール名。</span><span class="sxs-lookup"><span data-stu-id="adba8-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="adba8-107">[out]一意の識別子へのポインター、`IStream`読み込まれたモジュールを格納しています。</span><span class="sxs-lookup"><span data-stu-id="adba8-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="adba8-108">[out]アドレスへのポインター、`IStream`を読み込む、ポータブル実行可能 (PE) イメージを含むオブジェクト。 または、モジュールが見つからなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="adba8-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="adba8-109">[out]アドレスへのポインター、 `IStream` 、要求されたモジュールのプログラムのデバッグ (PDB) の情報が含まれるオブジェクト。 または、.pdb ファイルが見つかりませんでした場合は null です。</span><span class="sxs-lookup"><span data-stu-id="adba8-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adba8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="adba8-110">Return Value</span></span>  
  
|<span data-ttu-id="adba8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adba8-111">HRESULT</span></span>|<span data-ttu-id="adba8-112">説明</span><span class="sxs-lookup"><span data-stu-id="adba8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adba8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="adba8-113">S_OK</span></span>|<span data-ttu-id="adba8-114">`ProvideModule` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="adba8-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="adba8-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adba8-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adba8-116">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="adba8-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adba8-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adba8-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adba8-118">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="adba8-118">The call timed out.</span></span>|  
|<span data-ttu-id="adba8-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adba8-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adba8-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="adba8-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adba8-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adba8-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adba8-122">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="adba8-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adba8-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adba8-123">E_FAIL</span></span>|<span data-ttu-id="adba8-124">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="adba8-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adba8-125">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="adba8-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adba8-126">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="adba8-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="adba8-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="adba8-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="adba8-128">要求されたアセンブリまたはリンクされたリソースを配置できませんでした。</span><span class="sxs-lookup"><span data-stu-id="adba8-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="adba8-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="adba8-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="adba8-130">`pdwModuleId` ホストを返す必要がある識別子を格納するのに十分な大きさがありません。</span><span class="sxs-lookup"><span data-stu-id="adba8-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adba8-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="adba8-131">Remarks</span></span>  
 <span data-ttu-id="adba8-132">Id 値が返される`pdwModuleId`ホストによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="adba8-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="adba8-133">識別子は、プロセスの有効期間内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="adba8-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="adba8-134">CLR では、関連付けられているストリームの一意識別子としてこの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="adba8-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="adba8-135">値に対して各値をチェック`pAssemblyId`への呼び出しによって返される[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)の値に対して、`pdwModuleId`するその他の呼び出しによって返される`ProvideModule`します。</span><span class="sxs-lookup"><span data-stu-id="adba8-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="adba8-136">別のホストが同じ識別子の値を返す場合`IStream`CLR は、そのストリームの内容が既にマップされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="adba8-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="adba8-137">そうである場合、CLR は、新しいものをマップする代わりに、イメージの既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="adba8-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="adba8-138">そのため、識別子も重複してはなりませんから返されたアセンブリ識別子を持つ`ProvideAssembly`します。</span><span class="sxs-lookup"><span data-stu-id="adba8-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adba8-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="adba8-139">Requirements</span></span>  
 <span data-ttu-id="adba8-140">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adba8-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adba8-141">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="adba8-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adba8-142">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="adba8-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adba8-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adba8-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adba8-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="adba8-144">See also</span></span>

- [<span data-ttu-id="adba8-145">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="adba8-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="adba8-146">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="adba8-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="adba8-147">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="adba8-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
