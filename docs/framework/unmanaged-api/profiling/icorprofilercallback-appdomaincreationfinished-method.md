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
ms.openlocfilehash: 1cf3f2b62b388b6c2d6fcd75b1b07a67d5b2e49f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866703"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="09801-102">ICorProfilerCallback::AppDomainCreationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="09801-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="09801-103">アプリケーションドメインが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="09801-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09801-104">構文</span><span class="sxs-lookup"><span data-stu-id="09801-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="09801-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09801-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="09801-106">の \[] は、作成されたドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="09801-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="09801-107">\[] アプリケーションドメインの作成が正常に完了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="09801-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="09801-108">コメント</span><span class="sxs-lookup"><span data-stu-id="09801-108">Remarks</span></span>  
 <span data-ttu-id="09801-109">アプリケーション ID は、`AppDomainCreationFinished` メソッドが呼び出されるまで、情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="09801-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="09801-110">`AppDomainCreationFinished` コールバックの後も、アプリケーションドメインの読み込みの一部が続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="09801-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="09801-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="09801-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="09801-112">ただし、`hrStatus` の成功 HRESULT は、アプリケーションドメインの作成の最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="09801-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09801-113">要件</span><span class="sxs-lookup"><span data-stu-id="09801-113">Requirements</span></span>  
 <span data-ttu-id="09801-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09801-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09801-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09801-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09801-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09801-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09801-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09801-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09801-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="09801-118">See also</span></span>

- [<span data-ttu-id="09801-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09801-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
