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
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762430"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="e16e0-102">ICorConfiguration::AddDebuggerSpecialThread メソッド</span><span class="sxs-lookup"><span data-stu-id="e16e0-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="e16e0-103">デバッグサービスに対して、マネージまたはアンマネージのデバッグシナリオでデバッガーがアプリケーションを停止している間に、特定のスレッドの実行を継続できるようにする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e16e0-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e16e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e16e0-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e16e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e16e0-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="e16e0-106">から実行を継続することが許可されているスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="e16e0-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e16e0-107">解説</span><span class="sxs-lookup"><span data-stu-id="e16e0-107">Remarks</span></span>  
 <span data-ttu-id="e16e0-108">指定されたスレッドはマネージコードの実行を許可されないか、または任意の方法でランタイムに入ることができません。</span><span class="sxs-lookup"><span data-stu-id="e16e0-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="e16e0-109">このようなスレッドの例として、レガシスクリプトデバッガーをサポートするインプロセススレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="e16e0-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e16e0-110">要件</span><span class="sxs-lookup"><span data-stu-id="e16e0-110">Requirements</span></span>  
 <span data-ttu-id="e16e0-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e16e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e16e0-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e16e0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e16e0-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e16e0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e16e0-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e16e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16e0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e16e0-115">See also</span></span>

- [<span data-ttu-id="e16e0-116">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e16e0-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
