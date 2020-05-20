---
title: ICLRRuntimeHost::GetCLRControl メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 68bcdc33e34075cc5876ee721ef57282cdaa6e86
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703684"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="b44e8-102">ICLRRuntimeHost::GetCLRControl メソッド</span><span class="sxs-lookup"><span data-stu-id="b44e8-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="b44e8-103">ホストが共通言語ランタイム (CLR) の側面をカスタマイズするために使用できる[ICLRControl interface](iclrcontrol-interface.md)型のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b44e8-103">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="b44e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b44e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b44e8-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="b44e8-106">入出力ホストが CLR の追加の側面を構成できるようにする[ICLRControl interface](iclrcontrol-interface.md)型のインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="b44e8-106">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b44e8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b44e8-107">Return Value</span></span>  
  
|<span data-ttu-id="b44e8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b44e8-108">HRESULT</span></span>|<span data-ttu-id="b44e8-109">説明</span><span class="sxs-lookup"><span data-stu-id="b44e8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b44e8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b44e8-110">S_OK</span></span>|<span data-ttu-id="b44e8-111">`GetCLRControl`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b44e8-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="b44e8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b44e8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b44e8-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b44e8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b44e8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b44e8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b44e8-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b44e8-115">The call timed out.</span></span>|  
|<span data-ttu-id="b44e8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b44e8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b44e8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b44e8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b44e8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b44e8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b44e8-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b44e8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b44e8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b44e8-120">E_FAIL</span></span>|<span data-ttu-id="b44e8-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b44e8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b44e8-122">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b44e8-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b44e8-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b44e8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b44e8-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b44e8-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b44e8-125">CLR は既に開始されています。</span><span class="sxs-lookup"><span data-stu-id="b44e8-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b44e8-126">解説</span><span class="sxs-lookup"><span data-stu-id="b44e8-126">Remarks</span></span>  
 <span data-ttu-id="b44e8-127">`ICLRControl`[Getclrmanager メソッド](iclrcontrol-getclrmanager-method.md)を提供します。このメソッドを使用すると、ホストは、マネージャーの型のいずれかへのインターフェイスポインターを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b44e8-127">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b44e8-128">要件</span><span class="sxs-lookup"><span data-stu-id="b44e8-128">Requirements</span></span>  
 <span data-ttu-id="b44e8-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b44e8-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b44e8-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b44e8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b44e8-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b44e8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b44e8-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b44e8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44e8-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b44e8-133">See also</span></span>

- [<span data-ttu-id="b44e8-134">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b44e8-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b44e8-135">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b44e8-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
