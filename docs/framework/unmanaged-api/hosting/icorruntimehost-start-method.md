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
ms.openlocfilehash: 5e6521f8013bf92f073ab4b6808871c95ac2802b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700112"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="f95ac-102">ICorRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="f95ac-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="f95ac-103">共通言語ランタイム (CLR) を開始します。</span><span class="sxs-lookup"><span data-stu-id="f95ac-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f95ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="f95ac-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f95ac-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f95ac-105">Return Value</span></span>  
  
|<span data-ttu-id="f95ac-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f95ac-106">HRESULT</span></span>|<span data-ttu-id="f95ac-107">説明</span><span class="sxs-lookup"><span data-stu-id="f95ac-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f95ac-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f95ac-108">S_OK</span></span>|<span data-ttu-id="f95ac-109">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f95ac-109">The operation was successful.</span></span>|  
|<span data-ttu-id="f95ac-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f95ac-110">S_FALSE</span></span>|<span data-ttu-id="f95ac-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f95ac-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f95ac-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f95ac-112">E_FAIL</span></span>|<span data-ttu-id="f95ac-113">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f95ac-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f95ac-114">メソッド E_FAIL が返された場合、CLR はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f95ac-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="f95ac-115">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f95ac-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f95ac-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f95ac-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f95ac-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="f95ac-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f95ac-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="f95ac-118">Remarks</span></span>  
 <span data-ttu-id="f95ac-119">呼び出す必要は通常、`Start`メソッド、ため、CLR はマネージ コードを実行する最初の要求時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="f95ac-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f95ac-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="f95ac-120">Requirements</span></span>  
 <span data-ttu-id="f95ac-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f95ac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f95ac-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f95ac-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f95ac-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f95ac-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f95ac-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="f95ac-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f95ac-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f95ac-125">See also</span></span>

- [<span data-ttu-id="f95ac-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f95ac-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
