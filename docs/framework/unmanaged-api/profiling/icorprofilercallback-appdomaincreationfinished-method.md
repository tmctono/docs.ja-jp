---
title: ICorProfilerCallback::AppDomainCreationFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177073"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="97149-102">ICorProfilerCallback::AppDomainCreationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="97149-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="97149-103">アプリケーション ドメインが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="97149-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97149-104">構文</span><span class="sxs-lookup"><span data-stu-id="97149-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="97149-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97149-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="97149-106">\[in] 作成されたドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="97149-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="97149-107">\[in] アプリケーション ドメインの作成が正常に完了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="97149-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="97149-108">解説</span><span class="sxs-lookup"><span data-stu-id="97149-108">Remarks</span></span>  
 <span data-ttu-id="97149-109">メソッドが呼び出されるまで、アプリケーション ID は`AppDomainCreationFinished`情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="97149-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="97149-110">アプリケーション ドメインの読み込みの一部`AppDomainCreationFinished`は、コールバック後も続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="97149-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="97149-111">エラー HRESULT`hrStatus`のエラーは、失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="97149-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="97149-112">ただし、成功した HRESULT`hrStatus`は、アプリケーション ドメインの作成の最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="97149-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97149-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="97149-113">Requirements</span></span>  
 <span data-ttu-id="97149-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97149-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97149-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97149-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97149-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97149-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97149-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97149-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97149-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="97149-118">See also</span></span>

- [<span data-ttu-id="97149-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97149-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
