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
ms.openlocfilehash: 76f56971223154d3ed966c272081049adf30de54
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500495"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="95124-102">ICorProfilerCallback::AppDomainCreationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="95124-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="95124-103">アプリケーションドメインが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="95124-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95124-104">構文</span><span class="sxs-lookup"><span data-stu-id="95124-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="95124-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95124-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="95124-106">\[in] は、作成されたドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="95124-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="95124-107">\[in] アプリケーションドメインの作成が正常に完了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="95124-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="95124-108">解説</span><span class="sxs-lookup"><span data-stu-id="95124-108">Remarks</span></span>  
 <span data-ttu-id="95124-109">アプリケーション ID は、メソッドが呼び出されるまで、情報要求に対して有効ではありません `AppDomainCreationFinished` 。</span><span class="sxs-lookup"><span data-stu-id="95124-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="95124-110">アプリケーションドメインの読み込みの一部は、コールバック後も続行される場合があり `AppDomainCreationFinished` ます。</span><span class="sxs-lookup"><span data-stu-id="95124-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="95124-111">のエラー HRESULT は `hrStatus` エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="95124-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="95124-112">ただし、の成功 HRESULT は、 `hrStatus` アプリケーションドメインの作成の最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="95124-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95124-113">要件</span><span class="sxs-lookup"><span data-stu-id="95124-113">Requirements</span></span>  
 <span data-ttu-id="95124-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95124-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95124-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95124-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95124-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95124-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95124-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95124-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95124-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="95124-118">See also</span></span>

- [<span data-ttu-id="95124-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95124-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
