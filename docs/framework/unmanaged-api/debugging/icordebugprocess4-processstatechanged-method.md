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
ms.openlocfilehash: adfd563e19389642ac0ed0a3cef4aae8a32fa466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767190"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="0f983-102">ICorDebugProcess4::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="0f983-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="0f983-103">デバッガーをプロセスの出力がデバッグ対象の実行を続行は ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="0f983-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f983-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f983-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="0f983-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f983-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="0f983-106">[in]メンバー、 [CorDebugStateChange 列挙体](cordebugstatechange-enumeration.md)プロセスの実行状態の変更を記述します。</span><span class="sxs-lookup"><span data-stu-id="0f983-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f983-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f983-107">Remarks</span></span>

<span data-ttu-id="0f983-108">指定されたメソッドは、`ICorDebugProcess4`インターフェイスし、仮想メソッド テーブルの 4 番目のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0f983-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f983-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f983-109">Requirements</span></span>

 <span data-ttu-id="0f983-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f983-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="0f983-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="0f983-111">**Header:** None</span></span>

 <span data-ttu-id="0f983-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="0f983-112">**Library:** None</span></span>
 
 <span data-ttu-id="0f983-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f983-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0f983-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f983-114">See also</span></span>

- [<span data-ttu-id="0f983-115">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f983-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="0f983-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f983-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0f983-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0f983-117">Debugging</span></span>](index.md)
