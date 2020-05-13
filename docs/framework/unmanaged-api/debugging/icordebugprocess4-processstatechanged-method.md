---
title: ICorDebugProcess4::P rocessStateChanged メソッド
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213570"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="879cf-102">ICorDebugProcess4::P rocessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="879cf-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="879cf-103">アウトプロセスデバッガーがデバッグ対象の実行を継続していることを ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="879cf-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="879cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="879cf-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="879cf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="879cf-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="879cf-106">からプロセスの実行状態の変更を記述する[CorDebugStateChange 列挙体](cordebugstatechange-enumeration.md)のメンバー。</span><span class="sxs-lookup"><span data-stu-id="879cf-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="879cf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="879cf-107">Remarks</span></span>

<span data-ttu-id="879cf-108">指定されたメソッドはインターフェイスの一部で `ICorDebugProcess4` あり、仮想メソッドテーブルの4番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="879cf-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="879cf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="879cf-109">Requirements</span></span>

 <span data-ttu-id="879cf-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="879cf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="879cf-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="879cf-111">**Header:** None</span></span>

 <span data-ttu-id="879cf-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="879cf-112">**Library:** None</span></span>

 <span data-ttu-id="879cf-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="879cf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="879cf-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="879cf-114">See also</span></span>

- [<span data-ttu-id="879cf-115">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="879cf-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="879cf-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="879cf-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="879cf-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="879cf-117">Debugging</span></span>](index.md)
