---
title: ICorDebugManagedCallback::ControlCTrap メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e0217019aa9b8ff85716c62c27c0f4d5547074a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759794"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="c8cd3-102">ICorDebugManagedCallback::ControlCTrap メソッド</span><span class="sxs-lookup"><span data-stu-id="c8cd3-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="c8cd3-103">CTRL + C が、デバッグ対象プロセスでトラップされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cd3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8cd3-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8cd3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8cd3-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c8cd3-106">[in]CTRL + C をトラップするプロセスを表す ICorDebugProcess オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8cd3-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c8cd3-107">Return Value</span></span>  
  
|<span data-ttu-id="c8cd3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8cd3-108">HRESULT</span></span>|<span data-ttu-id="c8cd3-109">説明</span><span class="sxs-lookup"><span data-stu-id="c8cd3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8cd3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8cd3-110">S_OK</span></span>|<span data-ttu-id="c8cd3-111">デバッガーでは、CTRL + C トラップを処理します。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="c8cd3-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c8cd3-112">S_FALSE</span></span>|<span data-ttu-id="c8cd3-113">デバッガーでは、CTRL + C トラップは処理されません。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8cd3-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8cd3-114">Remarks</span></span>  
 <span data-ttu-id="c8cd3-115">このコールバックは、プロセス内のすべてのアプリケーション ドメインが停止しました。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8cd3-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8cd3-116">Requirements</span></span>  
 <span data-ttu-id="c8cd3-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8cd3-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8cd3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8cd3-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8cd3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8cd3-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8cd3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8cd3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8cd3-121">See also</span></span>

- [<span data-ttu-id="c8cd3-122">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8cd3-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
