---
title: CorDebugStateChange 列挙体
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723070"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="a905c-102">CorDebugStateChange 列挙体</span><span class="sxs-lookup"><span data-stu-id="a905c-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="a905c-103">プロセスへの変更に基づいて破棄が必要となった、キャッシュされたデータの量を示します。</span><span class="sxs-lookup"><span data-stu-id="a905c-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="a905c-104">構文</span><span class="sxs-lookup"><span data-stu-id="a905c-104">Syntax</span></span>

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="a905c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a905c-105">Members</span></span>

| <span data-ttu-id="a905c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a905c-106">Member</span></span>            | <span data-ttu-id="a905c-107">説明</span><span class="sxs-lookup"><span data-stu-id="a905c-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="a905c-108">プロセスはフォワード実行によって新しいメモリ状態に達しています。</span><span class="sxs-lookup"><span data-stu-id="a905c-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="a905c-109">プロセスのメモリは、以前とは異なる状態になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a905c-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a905c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a905c-110">Remarks</span></span>

 <span data-ttu-id="a905c-111">メンバー、`CorDebugStateChange`デバッガーを呼び出すと、列挙型が、引数として指定された、`ProcessStateChanged`メソッドで[ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md)または[ICorDebugProcess6:。ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="a905c-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="a905c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a905c-112">Requirements</span></span>

 <span data-ttu-id="a905c-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a905c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="a905c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a905c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="a905c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a905c-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="a905c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a905c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a905c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a905c-117">See also</span></span>

- [<span data-ttu-id="a905c-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="a905c-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a905c-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a905c-119">Debugging</span></span>](index.md)
