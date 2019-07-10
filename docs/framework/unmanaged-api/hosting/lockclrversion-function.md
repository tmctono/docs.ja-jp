---
title: LockClrVersion 関数
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6742293c1970198ef3d5f5da7d75a0c78e78045c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768410"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="3652a-102">LockClrVersion 関数</span><span class="sxs-lookup"><span data-stu-id="3652a-102">LockClrVersion Function</span></span>
<span data-ttu-id="3652a-103">により、ホストがプロセス内で、CLR を明示的に初期化する前に使用する共通言語ランタイム (CLR) のバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="3652a-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="3652a-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="3652a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3652a-105">構文</span><span class="sxs-lookup"><span data-stu-id="3652a-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3652a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3652a-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="3652a-107">[in]初期化時に CLR によって呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="3652a-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="3652a-108">[in]初期化の CLR に通知するためにホストによって呼び出される関数を開始しています。</span><span class="sxs-lookup"><span data-stu-id="3652a-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="3652a-109">[in]初期化の CLR に通知するためにホストによって呼び出される関数が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3652a-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3652a-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3652a-110">Return Value</span></span>  
 <span data-ttu-id="3652a-111">このメソッドは、次の値だけでなく、WinError.h で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="3652a-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3652a-112">リターン コード</span><span class="sxs-lookup"><span data-stu-id="3652a-112">Return code</span></span>|<span data-ttu-id="3652a-113">説明</span><span class="sxs-lookup"><span data-stu-id="3652a-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3652a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3652a-114">S_OK</span></span>|<span data-ttu-id="3652a-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="3652a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="3652a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3652a-116">E_INVALIDARG</span></span>|<span data-ttu-id="3652a-117">1 つ以上の引数が null です。</span><span class="sxs-lookup"><span data-stu-id="3652a-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3652a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="3652a-118">Remarks</span></span>  
 <span data-ttu-id="3652a-119">ホスト呼び出し`LockClrVersion`CLR を初期化する前にします。</span><span class="sxs-lookup"><span data-stu-id="3652a-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="3652a-120">`LockClrVersion` すべてがコールバック型の 3 つのパラメーターを受け取る[FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)します。</span><span class="sxs-lookup"><span data-stu-id="3652a-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="3652a-121">この種類の定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3652a-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="3652a-122">次の手順は、ランタイムの初期化時に発生します。</span><span class="sxs-lookup"><span data-stu-id="3652a-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="3652a-123">ホスト呼び出し[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)またはその他のランタイム初期化関数の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="3652a-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="3652a-124">または、ホストは、COM オブジェクトのアクティベーションを使用してランタイムを初期化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3652a-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="3652a-125">ランタイムがで指定された関数を呼び出す、`hostCallback`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3652a-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="3652a-126">指定された関数`hostCallback`続いて、次の一連の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="3652a-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="3652a-127">指定された関数、`pBeginHostSetup`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3652a-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="3652a-128">`CorBindToRuntimeEx` (または別のランタイム初期化関数)。</span><span class="sxs-lookup"><span data-stu-id="3652a-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="3652a-129">[Iclrruntimehost::sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="3652a-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="3652a-130">[Iclrruntimehost::start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="3652a-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="3652a-131">指定された関数、`pEndHostSetup`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3652a-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="3652a-132">すべての呼び出し`pBeginHostSetup`に`pEndHostSetup`1 つのスレッドまたはファイバーは、同じ論理スタックで発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3652a-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="3652a-133">このスレッドは、対象スレッドと異なる場合が`hostCallback`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3652a-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3652a-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="3652a-134">Requirements</span></span>  
 <span data-ttu-id="3652a-135">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3652a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3652a-136">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3652a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3652a-137">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3652a-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3652a-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3652a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3652a-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3652a-139">See also</span></span>

- [<span data-ttu-id="3652a-140">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="3652a-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
