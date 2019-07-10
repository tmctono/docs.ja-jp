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
ms.openlocfilehash: 9290fd70b17b5a6456d85cb4b037ebbc62e028f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763979"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="3993a-102">IHostAssemblyStore::ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="3993a-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="3993a-103">アセンブリまたは、リンクされた (ただし、埋め込まれたされません) 内のモジュールのリソース ファイルを解決します。</span><span class="sxs-lookup"><span data-stu-id="3993a-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3993a-104">構文</span><span class="sxs-lookup"><span data-stu-id="3993a-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3993a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3993a-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="3993a-106">[in]ポインターを[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 、要求されたモジュールを記述するインスタンス<xref:System.AppDomain>アセンブリとモジュール名。</span><span class="sxs-lookup"><span data-stu-id="3993a-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="3993a-107">[out]一意の識別子へのポインター、`IStream`読み込まれたモジュールを格納しています。</span><span class="sxs-lookup"><span data-stu-id="3993a-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="3993a-108">[out]アドレスへのポインター、`IStream`を読み込む、ポータブル実行可能 (PE) イメージを含むオブジェクト。 または、モジュールが見つからなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="3993a-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="3993a-109">[out]アドレスへのポインター、 `IStream` 、要求されたモジュールのプログラムのデバッグ (PDB) の情報が含まれるオブジェクト。 または、.pdb ファイルが見つかりませんでした場合は null です。</span><span class="sxs-lookup"><span data-stu-id="3993a-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3993a-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3993a-110">Return Value</span></span>  
  
|<span data-ttu-id="3993a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3993a-111">HRESULT</span></span>|<span data-ttu-id="3993a-112">説明</span><span class="sxs-lookup"><span data-stu-id="3993a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3993a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3993a-113">S_OK</span></span>|<span data-ttu-id="3993a-114">`ProvideModule` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="3993a-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="3993a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3993a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3993a-116">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="3993a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3993a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3993a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3993a-118">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="3993a-118">The call timed out.</span></span>|  
|<span data-ttu-id="3993a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3993a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3993a-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3993a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3993a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3993a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3993a-122">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="3993a-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3993a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3993a-123">E_FAIL</span></span>|<span data-ttu-id="3993a-124">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3993a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3993a-125">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3993a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3993a-126">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3993a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3993a-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="3993a-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="3993a-128">要求されたアセンブリまたはリンクされたリソースを配置できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3993a-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="3993a-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3993a-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3993a-130">`pdwModuleId` ホストを返す必要がある識別子を格納するのに十分な大きさがありません。</span><span class="sxs-lookup"><span data-stu-id="3993a-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3993a-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="3993a-131">Remarks</span></span>  
 <span data-ttu-id="3993a-132">Id 値が返される`pdwModuleId`ホストによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="3993a-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="3993a-133">識別子は、プロセスの有効期間内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3993a-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="3993a-134">CLR では、関連付けられているストリームの一意識別子としてこの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="3993a-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="3993a-135">値に対して各値をチェック`pAssemblyId`への呼び出しによって返される[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)の値に対して、`pdwModuleId`するその他の呼び出しによって返される`ProvideModule`します。</span><span class="sxs-lookup"><span data-stu-id="3993a-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="3993a-136">別のホストが同じ識別子の値を返す場合`IStream`CLR は、そのストリームの内容が既にマップされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3993a-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="3993a-137">そうである場合、CLR は、新しいものをマップする代わりに、イメージの既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3993a-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="3993a-138">そのため、識別子も重複してはなりませんから返されたアセンブリ識別子を持つ`ProvideAssembly`します。</span><span class="sxs-lookup"><span data-stu-id="3993a-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3993a-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="3993a-139">Requirements</span></span>  
 <span data-ttu-id="3993a-140">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3993a-141">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3993a-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3993a-142">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3993a-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3993a-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3993a-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3993a-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3993a-144">See also</span></span>

- [<span data-ttu-id="3993a-145">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3993a-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3993a-146">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3993a-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="3993a-147">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3993a-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
