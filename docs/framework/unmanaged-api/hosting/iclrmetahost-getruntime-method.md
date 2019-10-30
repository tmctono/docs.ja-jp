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
ms.openlocfilehash: eb305aaa18fcb8dc63e3090297aabc8defc3a401
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140938"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="e5d76-102">ICLRMetaHost::GetRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e5d76-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="e5d76-103">共通言語ランタイム (CLR) の特定のバージョンに対応する[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5d76-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="e5d76-104">このメソッドは、 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)フラグと共に使用される[Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e5d76-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d76-105">構文</span><span class="sxs-lookup"><span data-stu-id="e5d76-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5d76-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5d76-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="e5d76-107">からメタデータに格納されている .NET Framework のコンパイルバージョン。 "v*A と*いう形式になります。*B*[.*X*] "</span><span class="sxs-lookup"><span data-stu-id="e5d76-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="e5d76-108">*A*、 *B*、および*X*は、メジャーバージョン、マイナーバージョン、およびビルド番号に対応する10進数です。</span><span class="sxs-lookup"><span data-stu-id="e5d76-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5d76-109">このパラメーターは、C:\windows\ microsoft.net \framework または C:\Windows\Microsoft.NET\Framework64. の下に表示される .NET Framework バージョンのディレクトリ名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d76-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="e5d76-110">値の例としては、"v v1.0.3705"、"v 1.1.4322"、"v v2.0.50727"、および "v4.0" があります。*X*"。ここで*x*は、インストールされているビルド番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="e5d76-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="e5d76-111">"V" プレフィックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5d76-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="e5d76-112">から目的のインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="e5d76-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="e5d76-113">現時点では、このパラメーターの有効な値は IID_ICLRRuntimeInfo のみです。</span><span class="sxs-lookup"><span data-stu-id="e5d76-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="e5d76-114">入出力要求されたランタイムに対応する[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5d76-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5d76-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="e5d76-115">Return Value</span></span>  
 <span data-ttu-id="e5d76-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="e5d76-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e5d76-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5d76-117">HRESULT</span></span>|<span data-ttu-id="e5d76-118">説明</span><span class="sxs-lookup"><span data-stu-id="e5d76-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5d76-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5d76-119">S_OK</span></span>|<span data-ttu-id="e5d76-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="e5d76-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="e5d76-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e5d76-121">E_POINTER</span></span>|<span data-ttu-id="e5d76-122">`pwzVersion` または `ppRuntime` が null です。</span><span class="sxs-lookup"><span data-stu-id="e5d76-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d76-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5d76-123">Remarks</span></span>  
 <span data-ttu-id="e5d76-124">このメソッドは、 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)インターフェイスや、非推奨の `CorBindTo*` 関数などのレガシ関数などのレガシインターフェイスと常に相互作用します (.NET Framework 2.0 ホスティング API の[非推奨の CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e5d76-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="e5d76-125">つまり、レガシ API で読み込まれたランタイムは新しい API から参照でき、新しい API で読み込まれたランタイムはレガシ API から参照できます。</span><span class="sxs-lookup"><span data-stu-id="e5d76-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d76-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="e5d76-126">Requirements</span></span>  
 <span data-ttu-id="e5d76-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d76-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d76-128">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="e5d76-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e5d76-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e5d76-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5d76-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d76-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d76-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5d76-131">See also</span></span>

- [<span data-ttu-id="e5d76-132">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5d76-132">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="e5d76-133">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="e5d76-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="e5d76-134">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5d76-134">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="e5d76-135">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="e5d76-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="e5d76-136">ホスティング</span><span class="sxs-lookup"><span data-stu-id="e5d76-136">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
