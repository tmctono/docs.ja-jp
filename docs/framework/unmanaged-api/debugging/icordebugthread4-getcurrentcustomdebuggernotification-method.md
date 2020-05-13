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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378696"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="af24d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="af24d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="af24d-103">現在のスレッドの現在の[ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="af24d-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="af24d-104">構文</span><span class="sxs-lookup"><span data-stu-id="af24d-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="af24d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af24d-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="af24d-106">入出力現在のスレッド上の現在のオブジェクトへのポインター `ICorDebugManagedCallback3::CustomNotification` 。</span><span class="sxs-lookup"><span data-stu-id="af24d-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="af24d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="af24d-107">Remarks</span></span>

<span data-ttu-id="af24d-108">`ppNotificationObject`コールバック内からメソッドが呼び出されていない場合 `ICorDebugManagedCallback3::CustomNotification` 、または現在の通知オブジェクトが存在しない場合は、の値が null になります。</span><span class="sxs-lookup"><span data-stu-id="af24d-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="af24d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="af24d-109">Requirements</span></span>

<span data-ttu-id="af24d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af24d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="af24d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af24d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="af24d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af24d-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="af24d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af24d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="af24d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="af24d-114">See also</span></span>

- [<span data-ttu-id="af24d-115">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af24d-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="af24d-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="af24d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="af24d-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="af24d-117">Debugging</span></span>](index.md)
