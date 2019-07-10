---
title: ICLRMetaHost::GetRuntime メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99b87ca1af6c8e88173624f544117eee700fba17
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779774"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="12053-102">ICLRMetaHost::GetRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="12053-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="12053-103">取得、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)共通言語ランタイム (CLR) の特定のバージョンに対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="12053-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="12053-104">このメソッドは、 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)で使用される関数、 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)フラグ。</span><span class="sxs-lookup"><span data-stu-id="12053-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12053-105">構文</span><span class="sxs-lookup"><span data-stu-id="12053-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12053-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12053-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="12053-107">[in]形式で、メタデータに格納されている .NET Framework のコンパイル バージョン"v*A*.*B*[.*X*]"。</span><span class="sxs-lookup"><span data-stu-id="12053-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="12053-108">*A*、 *B*、および*X*はメジャー バージョン、マイナー バージョン、およびビルド番号に対応する 10 進数。</span><span class="sxs-lookup"><span data-stu-id="12053-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12053-109">C:\Windows\Microsoft.NET\Framework または C:\Windows\Microsoft.NET\Framework64 で表示される、このパラメーターは .NET Framework のバージョンのディレクトリ名に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12053-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="12053-110">例の値は、"v1.0.3705"、"v1.1.4322"、"v2.0.50727"および"v4.0 です。*X*"ここで、 *X*インストールされているビルドの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="12053-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="12053-111">"V"プレフィックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="12053-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="12053-112">[in]必要なインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="12053-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="12053-113">現時点では、このパラメーターの唯一の有効な値は、IID_ICLRRuntimeInfo です。</span><span class="sxs-lookup"><span data-stu-id="12053-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="12053-114">[out]ポインター、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)要求されたランタイムに対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="12053-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12053-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="12053-115">Return Value</span></span>  
 <span data-ttu-id="12053-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="12053-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="12053-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12053-117">HRESULT</span></span>|<span data-ttu-id="12053-118">説明</span><span class="sxs-lookup"><span data-stu-id="12053-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12053-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="12053-119">S_OK</span></span>|<span data-ttu-id="12053-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="12053-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="12053-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="12053-121">E_POINTER</span></span>|<span data-ttu-id="12053-122">`pwzVersion` または `ppRuntime` が null です。</span><span class="sxs-lookup"><span data-stu-id="12053-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12053-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="12053-123">Remarks</span></span>  
 <span data-ttu-id="12053-124">このメソッドとやり取り一貫して従来のインターフェイスなど、 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)インターフェイスおよび従来の関数など、非推奨`CorBindTo*`関数 (を参照してください[非推奨の CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) API をホストしている .NET Framework 2.0 で)。</span><span class="sxs-lookup"><span data-stu-id="12053-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="12053-125">レガシ API で読み込まれたランタイムは、新しい API に表示されると、新しい API が読み込まれているランタイムがレガシ API に表示されます。</span><span class="sxs-lookup"><span data-stu-id="12053-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12053-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="12053-126">Requirements</span></span>  
 <span data-ttu-id="12053-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12053-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12053-128">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="12053-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="12053-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="12053-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12053-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12053-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12053-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="12053-131">See also</span></span>

- [<span data-ttu-id="12053-132">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12053-132">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="12053-133">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="12053-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="12053-134">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12053-134">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="12053-135">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="12053-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="12053-136">ホスティング</span><span class="sxs-lookup"><span data-stu-id="12053-136">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
