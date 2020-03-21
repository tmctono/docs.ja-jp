---
title: メソッドを変更 :Pしました。
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178626"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="4744b-102">メソッドを変更 :Pしました。</span><span class="sxs-lookup"><span data-stu-id="4744b-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="4744b-103">プロセス外のデバッガーがデバッグ先の実行を続行していることを ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="4744b-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="4744b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4744b-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="4744b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4744b-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="4744b-106">[in]プロセスの実行状態の変更を記述する[列挙体](cordebugstatechange-enumeration.md)のメンバー。</span><span class="sxs-lookup"><span data-stu-id="4744b-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="4744b-107">解説</span><span class="sxs-lookup"><span data-stu-id="4744b-107">Remarks</span></span>

<span data-ttu-id="4744b-108">指定されたメソッドはインターフェイスの`ICorDebugProcess4`一部であり、仮想メソッド テーブルの 4 番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="4744b-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4744b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4744b-109">Requirements</span></span>

 <span data-ttu-id="4744b-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4744b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4744b-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="4744b-111">**Header:** None</span></span>

 <span data-ttu-id="4744b-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="4744b-112">**Library:** None</span></span>

 <span data-ttu-id="4744b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4744b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4744b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4744b-114">See also</span></span>

- [<span data-ttu-id="4744b-115">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4744b-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="4744b-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4744b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4744b-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4744b-117">Debugging</span></span>](index.md)
