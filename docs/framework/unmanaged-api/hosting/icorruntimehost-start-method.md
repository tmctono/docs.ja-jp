---
title: ICorRuntimeHost::Start メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: c450d83669a3bc548c15ed5800dc73438b9a84a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127691"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="2a7f4-102">ICorRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="2a7f4-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="2a7f4-103">共通言語ランタイム (CLR) を開始します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a7f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a7f4-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2a7f4-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a7f4-105">Return Value</span></span>  
  
|<span data-ttu-id="2a7f4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a7f4-106">HRESULT</span></span>|<span data-ttu-id="2a7f4-107">説明</span><span class="sxs-lookup"><span data-stu-id="2a7f4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a7f4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a7f4-108">S_OK</span></span>|<span data-ttu-id="2a7f4-109">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-109">The operation was successful.</span></span>|  
|<span data-ttu-id="2a7f4-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2a7f4-110">S_FALSE</span></span>|<span data-ttu-id="2a7f4-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2a7f4-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a7f4-112">E_FAIL</span></span>|<span data-ttu-id="2a7f4-113">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2a7f4-114">メソッドから E_FAIL が返された場合、このプロセスでは CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="2a7f4-115">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2a7f4-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a7f4-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a7f4-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a7f4-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a7f4-118">Remarks</span></span>  
 <span data-ttu-id="2a7f4-119">通常は、マネージコードを実行する最初の要求時に CLR が自動的に開始するため、`Start` メソッドを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a7f4-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="2a7f4-120">Requirements</span></span>  
 <span data-ttu-id="2a7f4-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a7f4-122">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2a7f4-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a7f4-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2a7f4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a7f4-124">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="2a7f4-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7f4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a7f4-125">See also</span></span>

- [<span data-ttu-id="2a7f4-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a7f4-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
