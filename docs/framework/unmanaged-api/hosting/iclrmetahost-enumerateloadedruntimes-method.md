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
ms.openlocfilehash: 2e22b8a2d0213b3bd766d80218d6f396721a90e1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703770"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="4c484-102">ICLRMetaHost::EnumerateLoadedRuntimes メソッド</span><span class="sxs-lookup"><span data-stu-id="4c484-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="4c484-103">指定されたプロセスに読み込まれる共通言語ランタイム (CLR) の各バージョンの有効な[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイスポインターを含む列挙体を返します。</span><span class="sxs-lookup"><span data-stu-id="4c484-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="4c484-104">このメソッドは、 [Getversionfromprocess](getversionfromprocess-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="4c484-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c484-105">構文</span><span class="sxs-lookup"><span data-stu-id="4c484-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c484-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c484-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="4c484-107">から読み込まれたランタイムを検査するプロセスのハンドル。</span><span class="sxs-lookup"><span data-stu-id="4c484-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="4c484-108">入出力<xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>プロセスによって読み込まれる各 CLR に対応する[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)インターフェイスの列挙体。</span><span class="sxs-lookup"><span data-stu-id="4c484-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c484-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4c484-109">Return Value</span></span>  
 <span data-ttu-id="4c484-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="4c484-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4c484-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c484-111">HRESULT</span></span>|<span data-ttu-id="4c484-112">説明</span><span class="sxs-lookup"><span data-stu-id="4c484-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c484-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c484-113">S_OK</span></span>|<span data-ttu-id="4c484-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="4c484-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="4c484-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4c484-115">E_POINTER</span></span>|<span data-ttu-id="4c484-116">`ppEnumerator` が null です。</span><span class="sxs-lookup"><span data-stu-id="4c484-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c484-117">解説</span><span class="sxs-lookup"><span data-stu-id="4c484-117">Remarks</span></span>  
 <span data-ttu-id="4c484-118">このメソッドは、 [Corbindtoruntime](corbindtoruntime-function.md)などの非推奨の関数を使用して読み込まれた場合でも、読み込まれたすべてのランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4c484-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c484-119">要件</span><span class="sxs-lookup"><span data-stu-id="4c484-119">Requirements</span></span>  
 <span data-ttu-id="4c484-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c484-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c484-121">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="4c484-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4c484-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4c484-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c484-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c484-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c484-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c484-124">See also</span></span>

- [<span data-ttu-id="4c484-125">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c484-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="4c484-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4c484-126">Hosting</span></span>](index.md)
