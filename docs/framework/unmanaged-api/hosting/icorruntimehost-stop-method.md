---
title: ICorRuntimeHost::Stop メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: 5fcf8bc861b2ef0b8ea9f5a5e46585564cc26615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127703"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="870f7-102">ICorRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="870f7-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="870f7-103">現在のプロセスのランタイムでコードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="870f7-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="870f7-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="870f7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="870f7-105">Return Value</span></span>  
  
|<span data-ttu-id="870f7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="870f7-106">HRESULT</span></span>|<span data-ttu-id="870f7-107">説明</span><span class="sxs-lookup"><span data-stu-id="870f7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="870f7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="870f7-108">S_OK</span></span>|<span data-ttu-id="870f7-109">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="870f7-109">The operation was successful.</span></span>|  
|<span data-ttu-id="870f7-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="870f7-110">S_FALSE</span></span>|<span data-ttu-id="870f7-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="870f7-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="870f7-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="870f7-112">E_FAIL</span></span>|<span data-ttu-id="870f7-113">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="870f7-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="870f7-114">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="870f7-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="870f7-115">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="870f7-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="870f7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="870f7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="870f7-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="870f7-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="870f7-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="870f7-118">Remarks</span></span>  
 <span data-ttu-id="870f7-119">通常、`Stop` メソッドを呼び出す必要はありません。これは、プロセスが終了したときにコードが実行を停止するためです。</span><span class="sxs-lookup"><span data-stu-id="870f7-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="870f7-120">`Stop`を呼び出した後、CLR を同じプロセスに再初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="870f7-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870f7-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="870f7-121">Requirements</span></span>  
 <span data-ttu-id="870f7-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870f7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="870f7-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="870f7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="870f7-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="870f7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="870f7-125">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="870f7-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870f7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="870f7-126">See also</span></span>

- [<span data-ttu-id="870f7-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="870f7-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
