---
title: ICLRMetaHost::EnumerateLoadedRuntimes メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: f89307ad7ed41f872ad66a99be03663ac1f30f13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140971"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="7600a-102">ICLRMetaHost::EnumerateLoadedRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="7600a-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="7600a-103">指定されたプロセスに読み込まれる共通言語ランタイム (CLR) の各バージョンの有効な[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスポインターを含む列挙体を返します。</span><span class="sxs-lookup"><span data-stu-id="7600a-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="7600a-104">このメソッドは、 [Getversionfromprocess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="7600a-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7600a-105">構文</span><span class="sxs-lookup"><span data-stu-id="7600a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7600a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7600a-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="7600a-107">から読み込まれたランタイムを検査するプロセスのハンドル。</span><span class="sxs-lookup"><span data-stu-id="7600a-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="7600a-108">入出力プロセスによって読み込まれる各 CLR に対応する[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスの <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> 列挙体。</span><span class="sxs-lookup"><span data-stu-id="7600a-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7600a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7600a-109">Return Value</span></span>  
 <span data-ttu-id="7600a-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="7600a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7600a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7600a-111">HRESULT</span></span>|<span data-ttu-id="7600a-112">説明</span><span class="sxs-lookup"><span data-stu-id="7600a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7600a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7600a-113">S_OK</span></span>|<span data-ttu-id="7600a-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7600a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="7600a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7600a-115">E_POINTER</span></span>|<span data-ttu-id="7600a-116">`ppEnumerator` が null です。</span><span class="sxs-lookup"><span data-stu-id="7600a-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7600a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="7600a-117">Remarks</span></span>  
 <span data-ttu-id="7600a-118">このメソッドは、 [Corbindtoruntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)などの非推奨の関数を使用して読み込まれた場合でも、読み込まれたすべてのランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7600a-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7600a-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="7600a-119">Requirements</span></span>  
 <span data-ttu-id="7600a-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7600a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7600a-121">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="7600a-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7600a-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7600a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7600a-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7600a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7600a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7600a-124">See also</span></span>

- [<span data-ttu-id="7600a-125">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7600a-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="7600a-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7600a-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
