---
title: ICorDebugProcess4::ProcessStateChanged メソッド
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
ms.openlocfilehash: 5e3a6714489e2051a09b5855ab9f911ef2f57450
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632283"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="bf64e-102">ICorDebugProcess4::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="bf64e-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="bf64e-103">デバッガーをプロセスの出力がデバッグ対象の実行を続行は ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="bf64e-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf64e-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf64e-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="bf64e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf64e-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="bf64e-106">[in]メンバー、 [CorDebugStateChange 列挙体](cordebugstatechange-enumeration.md)プロセスの実行状態の変更を記述します。</span><span class="sxs-lookup"><span data-stu-id="bf64e-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf64e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf64e-107">Remarks</span></span>

<span data-ttu-id="bf64e-108">指定されたメソッドは、`ICorDebugProcess4`インターフェイスし、仮想メソッド テーブルの 4 番目のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="bf64e-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf64e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf64e-109">Requirements</span></span>

 <span data-ttu-id="bf64e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf64e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="bf64e-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="bf64e-111">**Header:** None</span></span>

 <span data-ttu-id="bf64e-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="bf64e-112">**Library:** None</span></span>
 
 <span data-ttu-id="bf64e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf64e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bf64e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf64e-114">See also</span></span>

- [<span data-ttu-id="bf64e-115">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf64e-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="bf64e-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf64e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="bf64e-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="bf64e-117">Debugging</span></span>](index.md)
