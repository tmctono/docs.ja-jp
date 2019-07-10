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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779901"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="d6458-102">ICorConfiguration::AddDebuggerSpecialThread メソッド</span><span class="sxs-lookup"><span data-stu-id="d6458-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="d6458-103">デバッグ サービスを特定のスレッドがデバッガーがマネージまたはアンマネージ デバッグ シナリオ中に停止したアプリケーションの実行を続行できることを示します。</span><span class="sxs-lookup"><span data-stu-id="d6458-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6458-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6458-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6458-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6458-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="d6458-106">[in]実行の継続を許可するかのスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="d6458-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6458-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6458-107">Remarks</span></span>  
 <span data-ttu-id="d6458-108">指定したスレッドをマネージ コードを実行したり任意の方法でランタイムに許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d6458-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="d6458-109">このようなスレッドの例は、従来のスクリプト デバッガーをサポートするために、プロセスのスレッドになります。</span><span class="sxs-lookup"><span data-stu-id="d6458-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6458-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6458-110">Requirements</span></span>  
 <span data-ttu-id="d6458-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6458-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6458-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d6458-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6458-113">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d6458-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6458-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6458-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6458-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6458-115">See also</span></span>

- [<span data-ttu-id="d6458-116">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6458-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
