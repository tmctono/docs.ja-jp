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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965966"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="a590a-102">ICorRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="a590a-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="a590a-103">現在のプロセスのランタイムでコードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="a590a-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a590a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a590a-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a590a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="a590a-105">Return Value</span></span>  
  
|<span data-ttu-id="a590a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a590a-106">HRESULT</span></span>|<span data-ttu-id="a590a-107">説明</span><span class="sxs-lookup"><span data-stu-id="a590a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a590a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a590a-108">S_OK</span></span>|<span data-ttu-id="a590a-109">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="a590a-109">The operation was successful.</span></span>|  
|<span data-ttu-id="a590a-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a590a-110">S_FALSE</span></span>|<span data-ttu-id="a590a-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a590a-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a590a-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a590a-112">E_FAIL</span></span>|<span data-ttu-id="a590a-113">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a590a-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a590a-114">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a590a-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a590a-115">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a590a-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a590a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a590a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a590a-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a590a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a590a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="a590a-118">Remarks</span></span>  
 <span data-ttu-id="a590a-119">通常、 `Stop`メソッドを呼び出す必要はありません。これは、プロセスが終了したときにコードが実行を停止するためです。</span><span class="sxs-lookup"><span data-stu-id="a590a-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a590a-120">を`Stop`呼び出した後、CLR を同じプロセスに再初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="a590a-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a590a-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="a590a-121">Requirements</span></span>  
 <span data-ttu-id="a590a-122">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a590a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a590a-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a590a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a590a-124">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a590a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a590a-125">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="a590a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a590a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a590a-126">See also</span></span>

- [<span data-ttu-id="a590a-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a590a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
