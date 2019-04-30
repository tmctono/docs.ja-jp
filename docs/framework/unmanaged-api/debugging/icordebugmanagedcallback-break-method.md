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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bab20301c5413f8bbe95d44b87e06d3b3870c9e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988367"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="eb33f-102">ICorDebugManagedCallback::Break メソッド</span><span class="sxs-lookup"><span data-stu-id="eb33f-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="eb33f-103">デバッガーに通知時に、<xref:System.Reflection.Emit.OpCodes.Break>コード ストリームに命令を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb33f-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb33f-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb33f-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="eb33f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb33f-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="eb33f-106">[in]中断命令を含むアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eb33f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="eb33f-107">[in]中断命令を含むスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eb33f-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb33f-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb33f-108">Requirements</span></span>

<span data-ttu-id="eb33f-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb33f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="eb33f-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb33f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="eb33f-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb33f-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="eb33f-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb33f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eb33f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb33f-113">See also</span></span>

- [<span data-ttu-id="eb33f-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb33f-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)