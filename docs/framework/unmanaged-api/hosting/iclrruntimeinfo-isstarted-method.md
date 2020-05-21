---
title: ICLRRuntimeInfo::IsStarted メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 85a7adddf395e07297c8fb6ceab4aa81e0aaf012
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762202"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="736fa-102">ICLRRuntimeInfo::IsStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="736fa-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="736fa-103">ランタイムが開始されたかどうか (つまり、 [ICLRRuntimeHost:: Start メソッド](iclrruntimehost-start-method.md)が呼び出され、成功したかどうか) を示します。</span><span class="sxs-lookup"><span data-stu-id="736fa-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="736fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="736fa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="736fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="736fa-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="736fa-106">[出力] `true`このランタイムが開始されている場合は。それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="736fa-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="736fa-107">入出力ランタイムを開始するために使用されたフラグを返します。</span><span class="sxs-lookup"><span data-stu-id="736fa-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="736fa-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="736fa-108">Return Value</span></span>  
 <span data-ttu-id="736fa-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="736fa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="736fa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="736fa-110">HRESULT</span></span>|<span data-ttu-id="736fa-111">説明</span><span class="sxs-lookup"><span data-stu-id="736fa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="736fa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="736fa-112">S_OK</span></span>|<span data-ttu-id="736fa-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="736fa-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="736fa-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="736fa-114">E_NOTIMPL</span></span>|<span data-ttu-id="736fa-115">共通言語ランタイム (CLR) のバージョンは、.NET Framework 4 の CLR バージョンよりも前のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="736fa-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="736fa-116">解説</span><span class="sxs-lookup"><span data-stu-id="736fa-116">Remarks</span></span>  
 <span data-ttu-id="736fa-117">このメソッドは、.NET Framework 4 の CLR バージョンより前の CLR バージョンでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="736fa-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="736fa-118">要件</span><span class="sxs-lookup"><span data-stu-id="736fa-118">Requirements</span></span>  
 <span data-ttu-id="736fa-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="736fa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="736fa-120">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="736fa-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="736fa-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="736fa-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="736fa-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="736fa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="736fa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="736fa-123">See also</span></span>

- [<span data-ttu-id="736fa-124">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="736fa-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="736fa-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="736fa-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="736fa-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="736fa-126">Hosting</span></span>](index.md)
