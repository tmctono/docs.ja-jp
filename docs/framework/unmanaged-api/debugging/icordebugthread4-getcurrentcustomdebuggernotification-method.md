---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f626ff6e562bd9bc94440f31e9470a45cc32cfbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216328"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="5f314-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="5f314-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="5f314-103">現在の取得[icordebugmanagedcallback 3::customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)現在のスレッド上のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f314-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f314-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f314-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="5f314-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f314-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="5f314-106">[out]現在へのポインター`ICorDebugManagedCallback3::CustomNotification`現在のスレッド上のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f314-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f314-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f314-107">Remarks</span></span>

<span data-ttu-id="5f314-108">値`ppNotificationObject`内からメソッドを呼び出さない場合は null を`ICorDebugManagedCallback3::CustomNotification`コールバック、または現在の通知オブジェクトが存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="5f314-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f314-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f314-109">Requirements</span></span>

<span data-ttu-id="5f314-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f314-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5f314-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f314-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="5f314-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f314-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5f314-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f314-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5f314-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f314-114">See also</span></span>

- [<span data-ttu-id="5f314-115">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f314-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="5f314-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f314-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5f314-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5f314-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
