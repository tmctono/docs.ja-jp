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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7615f5dad1666685333011503c5bef4c98a6a8bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771684"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="367a4-102">ICLRRuntimeInfo::IsLoaded メソッド</span><span class="sxs-lookup"><span data-stu-id="367a4-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="367a4-103">共通言語ランタイム (CLR) に関連付けられているかどうかを示す、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスが、プロセスに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="367a4-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="367a4-104">ランタイムも開始されないまま読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="367a4-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367a4-105">構文</span><span class="sxs-lookup"><span data-stu-id="367a4-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="367a4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="367a4-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="367a4-107">[in]プロセスへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="367a4-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="367a4-108">[out]`true` 、CLR がプロセスに読み込まれます。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="367a4-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="367a4-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="367a4-109">Return Value</span></span>  
 <span data-ttu-id="367a4-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="367a4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="367a4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="367a4-111">HRESULT</span></span>|<span data-ttu-id="367a4-112">説明</span><span class="sxs-lookup"><span data-stu-id="367a4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="367a4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="367a4-113">S_OK</span></span>|<span data-ttu-id="367a4-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="367a4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="367a4-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="367a4-115">E_POINTER</span></span>|<span data-ttu-id="367a4-116">`pbLoaded` が null です。</span><span class="sxs-lookup"><span data-stu-id="367a4-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="367a4-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="367a4-117">Remarks</span></span>  
 <span data-ttu-id="367a4-118">このメソッドは、旧バージョンと互換性のある次の関数とインターフェイスで。</span><span class="sxs-lookup"><span data-stu-id="367a4-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="367a4-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (.NET Framework バージョン 1 ホスティング API) のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="367a4-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="367a4-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)インターフェイス (API をホストしている .NET Framework 2.0) にします。</span><span class="sxs-lookup"><span data-stu-id="367a4-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="367a4-121">非推奨`CorBindTo*`関数 (を参照してください[CLR ホスト関数の非推奨とされます](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)API をホストしている .NET Framework 2.0 で)。</span><span class="sxs-lookup"><span data-stu-id="367a4-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="367a4-122">ホストは、非推奨のいずれかを呼び出すことができます`CorBindTo*`などの関数、 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)関数、CLR の特定のバージョンのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="367a4-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="367a4-123">ホストが呼び出す可能性がありますし、 [iclrmetahost::getruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)メソッドを取得する同じバージョン番号を指定し、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="367a4-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="367a4-124">ホストが、呼び出した場合、`IsLoaded`メソッドで返された[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイス、`pbLoaded`返します`true`。 それ以外が返されます`false`。</span><span class="sxs-lookup"><span data-stu-id="367a4-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="367a4-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="367a4-125">Requirements</span></span>  
 <span data-ttu-id="367a4-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="367a4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="367a4-127">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="367a4-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="367a4-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="367a4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="367a4-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="367a4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367a4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="367a4-130">See also</span></span>

- [<span data-ttu-id="367a4-131">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="367a4-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="367a4-132">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="367a4-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="367a4-133">ホスティング</span><span class="sxs-lookup"><span data-stu-id="367a4-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
