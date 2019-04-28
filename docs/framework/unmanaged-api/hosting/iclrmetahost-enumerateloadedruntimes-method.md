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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0e1213128f5728f17225fbf6906d877dc64e86d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61919296"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="5ab8f-102">ICLRMetaHost::EnumerateLoadedRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="5ab8f-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="5ab8f-103">含む、有効な列挙体を返します[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)特定のプロセスに読み込まれる共通言語ランタイム (CLR) の各バージョン用のインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="5ab8f-104">このメソッドは、 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab8f-105">構文</span><span class="sxs-lookup"><span data-stu-id="5ab8f-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab8f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ab8f-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="5ab8f-107">[in]検査するプロセスのハンドルには、ランタイムが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="5ab8f-108">[out]<xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>の列挙体[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)プロセスによって読み込まれる各 CLR に対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ab8f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5ab8f-109">Return Value</span></span>  
 <span data-ttu-id="5ab8f-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5ab8f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ab8f-111">HRESULT</span></span>|<span data-ttu-id="5ab8f-112">説明</span><span class="sxs-lookup"><span data-stu-id="5ab8f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ab8f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ab8f-113">S_OK</span></span>|<span data-ttu-id="5ab8f-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="5ab8f-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5ab8f-115">E_POINTER</span></span>|<span data-ttu-id="5ab8f-116">`ppEnumerator` が null です。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ab8f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ab8f-117">Remarks</span></span>  
 <span data-ttu-id="5ab8f-118">非推奨の関数をなど、読み込まれていた場合でも、このメソッドは、リストをすべて読み込むランタイム[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab8f-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ab8f-119">Requirements</span></span>  
 <span data-ttu-id="5ab8f-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ab8f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab8f-121">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5ab8f-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5ab8f-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5ab8f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ab8f-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab8f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab8f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ab8f-124">See also</span></span>

- [<span data-ttu-id="5ab8f-125">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ab8f-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="5ab8f-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5ab8f-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
