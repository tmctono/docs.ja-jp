---
title: ICLRMetaHost インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb760f4923cc3530a28bc68180db743ee468b51d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140911"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="984dd-102">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="984dd-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="984dd-103">バージョン番号に基づいて特定のバージョンの共通言語ランタイム (CLR) を返すメソッド、すべてのインストールされた CLRs の一覧表示、指定されたプロセスで読み込まれたすべてのランタイムの一覧表示、アセンブリのコンパイルに使用される CLR バージョンの検出、プロセスの終了を行うメソッドを提供します。クリーンランタイムをシャットダウンし、従来の API バインディングにクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="984dd-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="984dd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-104">Methods</span></span>  
  
|<span data-ttu-id="984dd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-105">Method</span></span>|<span data-ttu-id="984dd-106">説明</span><span class="sxs-lookup"><span data-stu-id="984dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="984dd-107">EnumerateInstalledRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="984dd-108">コンピューターにインストールされている各 CLR バージョンの有効な[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスポインターを含む列挙を返します。</span><span class="sxs-lookup"><span data-stu-id="984dd-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="984dd-109">EnumerateLoadedRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="984dd-110">指定されたプロセスに読み込まれる各 CLR の有効な[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスポインターを含む列挙体を返します。</span><span class="sxs-lookup"><span data-stu-id="984dd-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="984dd-111">このメソッドは、 [Getversionfromprocess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="984dd-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="984dd-112">ExitProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="984dd-113">読み込まれたすべてのランタイムを正常にシャットダウンしてから、プロセスを終了しようとします。</span><span class="sxs-lookup"><span data-stu-id="984dd-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="984dd-114">[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="984dd-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="984dd-115">GetRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="984dd-116">特定の CLR バージョンに対応する[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="984dd-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="984dd-117">このメソッドは、 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)フラグと共に使用される[Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="984dd-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="984dd-118">GetVersionFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="984dd-119">ファイルパスを指定して、アセンブリの元の .NET Framework コンパイルバージョン (メタデータに格納されている) を取得します。</span><span class="sxs-lookup"><span data-stu-id="984dd-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="984dd-120">このメソッドは、 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="984dd-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="984dd-121">QueryLegacyV2RuntimeBinding メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="984dd-122">レガシアクティブ化ポリシーがバインドされているランタイムを表すインターフェイスを返します。たとえば、 [\<スタートアップ > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)構成ファイルエントリの `useLegacyV2RuntimeActivationPolicy` 属性を使用したり、レガシアクティベーション api を直接使用したり、レガシアクティブ化 api を直接使用したり、[ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)メソッドを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="984dd-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="984dd-123">RequestRuntimeLoadedNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="984dd-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="984dd-124">CLR バージョンが最初に読み込まれたが、まだ開始されていない場合は、指定された関数ポインターへのコールバックを保証します。</span><span class="sxs-lookup"><span data-stu-id="984dd-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="984dd-125">このメソッドは、 [Lockclrversion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="984dd-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="984dd-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="984dd-126">Remarks</span></span>  
 <span data-ttu-id="984dd-127">このインターフェイスのインスタンスを取得する唯一の方法は、 [Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数を次のように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="984dd-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="984dd-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="984dd-128">Requirements</span></span>  
 <span data-ttu-id="984dd-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984dd-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="984dd-130">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="984dd-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="984dd-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="984dd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="984dd-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="984dd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="984dd-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="984dd-133">See also</span></span>

- [<span data-ttu-id="984dd-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="984dd-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="984dd-135">ホスティング</span><span class="sxs-lookup"><span data-stu-id="984dd-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
