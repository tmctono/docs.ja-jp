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
ms.openlocfilehash: f70a88df00d15729a6bde06b49417b6439f7c0ec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212465"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="bd424-102">ICorDebugManagedCallback::Break メソッド</span><span class="sxs-lookup"><span data-stu-id="bd424-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="bd424-103"><xref:System.Reflection.Emit.OpCodes.Break>コードストリーム内の命令が実行されたときに、デバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bd424-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd424-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd424-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="bd424-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd424-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="bd424-106">からBreak 命令を含むアプリケーションドメインを表す、コードの Appdomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd424-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="bd424-107">からBreak 命令を含むスレッドを表す、コードスレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd424-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd424-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="bd424-108">Requirements</span></span>

<span data-ttu-id="bd424-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd424-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bd424-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd424-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="bd424-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd424-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bd424-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd424-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bd424-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd424-113">See also</span></span>

- [<span data-ttu-id="bd424-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd424-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
