---
title: ICorConfiguration::AddDebuggerSpecialThread メソッド
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127815"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="d4575-102">ICorConfiguration::AddDebuggerSpecialThread メソッド</span><span class="sxs-lookup"><span data-stu-id="d4575-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="d4575-103">デバッグサービスに対して、マネージまたはアンマネージのデバッグシナリオでデバッガーがアプリケーションを停止している間に、特定のスレッドの実行を継続できるようにする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="d4575-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4575-104">構文</span><span class="sxs-lookup"><span data-stu-id="d4575-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4575-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4575-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="d4575-106">から実行を継続することが許可されているスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="d4575-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4575-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4575-107">Remarks</span></span>  
 <span data-ttu-id="d4575-108">指定されたスレッドはマネージコードの実行を許可されないか、または任意の方法でランタイムに入ることができません。</span><span class="sxs-lookup"><span data-stu-id="d4575-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="d4575-109">このようなスレッドの例として、レガシスクリプトデバッガーをサポートするインプロセススレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d4575-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4575-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="d4575-110">Requirements</span></span>  
 <span data-ttu-id="d4575-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4575-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4575-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4575-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4575-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d4575-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4575-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4575-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4575-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4575-115">See also</span></span>

- [<span data-ttu-id="d4575-116">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4575-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
