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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ac86fdc0852c701b66986b6a304695fbdc8e755
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780395"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="d902b-102">ICorRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="d902b-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="d902b-103">共通言語ランタイム (CLR) を開始します。</span><span class="sxs-lookup"><span data-stu-id="d902b-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d902b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d902b-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d902b-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="d902b-105">Return Value</span></span>  
  
|<span data-ttu-id="d902b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d902b-106">HRESULT</span></span>|<span data-ttu-id="d902b-107">説明</span><span class="sxs-lookup"><span data-stu-id="d902b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d902b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d902b-108">S_OK</span></span>|<span data-ttu-id="d902b-109">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="d902b-109">The operation was successful.</span></span>|  
|<span data-ttu-id="d902b-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d902b-110">S_FALSE</span></span>|<span data-ttu-id="d902b-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d902b-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d902b-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d902b-112">E_FAIL</span></span>|<span data-ttu-id="d902b-113">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d902b-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d902b-114">メソッド E_FAIL が返された場合、CLR はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d902b-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="d902b-115">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d902b-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d902b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d902b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d902b-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d902b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d902b-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="d902b-118">Remarks</span></span>  
 <span data-ttu-id="d902b-119">呼び出す必要は通常、`Start`メソッド、ため、CLR はマネージ コードを実行する最初の要求時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="d902b-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d902b-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="d902b-120">Requirements</span></span>  
 <span data-ttu-id="d902b-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d902b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d902b-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d902b-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d902b-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d902b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d902b-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d902b-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d902b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d902b-125">See also</span></span>

- [<span data-ttu-id="d902b-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d902b-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
