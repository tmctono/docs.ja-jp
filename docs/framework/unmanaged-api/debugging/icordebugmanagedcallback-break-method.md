---
title: ICorDebugManagedCallback::Break メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122585"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="8702a-102">ICorDebugManagedCallback::Break メソッド</span><span class="sxs-lookup"><span data-stu-id="8702a-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="8702a-103">コードストリーム内の <xref:System.Reflection.Emit.OpCodes.Break> 命令が実行されたときに、デバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8702a-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="8702a-104">構文</span><span class="sxs-lookup"><span data-stu-id="8702a-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="8702a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8702a-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="8702a-106">からBreak 命令を含むアプリケーションドメインを表す、コードの Appdomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8702a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="8702a-107">からBreak 命令を含むスレッドを表す、コードスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8702a-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="8702a-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="8702a-108">Requirements</span></span>

<span data-ttu-id="8702a-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8702a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8702a-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8702a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8702a-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8702a-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8702a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8702a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8702a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8702a-113">See also</span></span>

- [<span data-ttu-id="8702a-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8702a-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
