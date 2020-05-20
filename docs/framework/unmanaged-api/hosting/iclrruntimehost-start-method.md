---
title: ICLRRuntimeHost::Start メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: e5ed1cbb640e760d75e1722871453a0bec283bde
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703904"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="65379-102">ICLRRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="65379-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="65379-103">共通言語ランタイム (CLR) をプロセスに初期化します。</span><span class="sxs-lookup"><span data-stu-id="65379-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65379-104">構文</span><span class="sxs-lookup"><span data-stu-id="65379-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="65379-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="65379-105">Return Value</span></span>  
  
|<span data-ttu-id="65379-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65379-106">HRESULT</span></span>|<span data-ttu-id="65379-107">説明</span><span class="sxs-lookup"><span data-stu-id="65379-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65379-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="65379-108">S_OK</span></span>|<span data-ttu-id="65379-109">`Start`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="65379-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="65379-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65379-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65379-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="65379-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65379-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65379-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65379-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="65379-113">The call timed out.</span></span>|  
|<span data-ttu-id="65379-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65379-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65379-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="65379-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65379-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65379-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65379-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="65379-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65379-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65379-118">E_FAIL</span></span>|<span data-ttu-id="65379-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="65379-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65379-120">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="65379-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65379-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="65379-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65379-122">解説</span><span class="sxs-lookup"><span data-stu-id="65379-122">Remarks</span></span>  
 <span data-ttu-id="65379-123">多くのシナリオでは、を呼び出す必要はありません。これは `Start` 、マネージコードを実行する最初の要求時にランタイムが自動的に初期化するためです。</span><span class="sxs-lookup"><span data-stu-id="65379-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="65379-124">ただし、を使用し `Start` て、ランタイムをいつ初期化するかを正確に指定できます。</span><span class="sxs-lookup"><span data-stu-id="65379-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65379-125">要件</span><span class="sxs-lookup"><span data-stu-id="65379-125">Requirements</span></span>  
 <span data-ttu-id="65379-126">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65379-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65379-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="65379-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65379-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="65379-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65379-129">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65379-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65379-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="65379-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="65379-131">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65379-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
