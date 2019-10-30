---
title: ICLRRuntimeInfo::IsLoaded メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136358"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="fe93e-102">ICLRRuntimeInfo::IsLoaded メソッド</span><span class="sxs-lookup"><span data-stu-id="fe93e-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="fe93e-103">[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスに関連付けられている共通言語ランタイム (CLR) をプロセスに読み込むかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fe93e-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="fe93e-104">ランタイムは、起動しなくても読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="fe93e-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe93e-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe93e-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe93e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe93e-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="fe93e-107">からプロセスを処理するハンドル。</span><span class="sxs-lookup"><span data-stu-id="fe93e-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="fe93e-108">[out] CLR がプロセスに読み込まれている場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="fe93e-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe93e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe93e-109">Return Value</span></span>  
 <span data-ttu-id="fe93e-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="fe93e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fe93e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe93e-111">HRESULT</span></span>|<span data-ttu-id="fe93e-112">説明</span><span class="sxs-lookup"><span data-stu-id="fe93e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe93e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe93e-113">S_OK</span></span>|<span data-ttu-id="fe93e-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="fe93e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="fe93e-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fe93e-115">E_POINTER</span></span>|<span data-ttu-id="fe93e-116">`pbLoaded` が null です。</span><span class="sxs-lookup"><span data-stu-id="fe93e-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe93e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe93e-117">Remarks</span></span>  
 <span data-ttu-id="fe93e-118">このメソッドは、次の関数およびインターフェイスと下位互換性があります。</span><span class="sxs-lookup"><span data-stu-id="fe93e-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="fe93e-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)インターフェイス (.NET Framework version 1 ホスティング API)。</span><span class="sxs-lookup"><span data-stu-id="fe93e-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="fe93e-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)インターフェイス (.NET Framework 2.0 ホスティング API)。</span><span class="sxs-lookup"><span data-stu-id="fe93e-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="fe93e-121">非推奨の `CorBindTo*` 関数 (.NET Framework 2.0 ホスティング API での[非推奨の CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fe93e-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="fe93e-122">ホストは、特定のバージョンの CLR をインスタンス化するために、 [Corbindtoruntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)関数など、非推奨の `CorBindTo*` 関数の1つを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe93e-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="fe93e-123">ホストは[ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)メソッドを呼び出し、同じバージョン番号を指定して[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="fe93e-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="fe93e-124">ホストが返された[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスで `IsLoaded` メソッドを呼び出した場合、`pbLoaded` は `true`を返します。それ以外の場合は `false`を返します。</span><span class="sxs-lookup"><span data-stu-id="fe93e-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe93e-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="fe93e-125">Requirements</span></span>  
 <span data-ttu-id="fe93e-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe93e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe93e-127">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="fe93e-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fe93e-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fe93e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe93e-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe93e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe93e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe93e-130">See also</span></span>

- [<span data-ttu-id="fe93e-131">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe93e-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fe93e-132">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe93e-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fe93e-133">ホスティング</span><span class="sxs-lookup"><span data-stu-id="fe93e-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
