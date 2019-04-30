---
title: DacpReJitData 構造体
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965938"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="829c2-102">DacpReJitData 構造体</span><span class="sxs-lookup"><span data-stu-id="829c2-102">DacpReJitData Structure</span></span>

<span data-ttu-id="829c2-103">指定されたプロファイラー インストルメント メソッドに関する基本情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="829c2-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="829c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="829c2-104">Syntax</span></span>

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="829c2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="829c2-105">Members</span></span>

| <span data-ttu-id="829c2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="829c2-106">Member</span></span>           | <span data-ttu-id="829c2-107">説明</span><span class="sxs-lookup"><span data-stu-id="829c2-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="829c2-108">メソッドの ReJit リビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="829c2-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="829c2-109">特定のバージョンのメソッドの ReJit インストルメンテーションの現在の状態を示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="829c2-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="829c2-110">メソッドの rejitted 実装のベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="829c2-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="829c2-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="829c2-111">Remarks</span></span>

<span data-ttu-id="829c2-112">この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="829c2-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="829c2-113">これを使用するには、上で指定した構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="829c2-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="829c2-114">使用して、構造体を定義する必要がありますも`ms_struct`Microsoft コンパイラを使用していない場合にパックします。</span><span class="sxs-lookup"><span data-stu-id="829c2-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="829c2-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="829c2-115">Requirements</span></span>
<span data-ttu-id="829c2-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="829c2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="829c2-117">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="829c2-117">**Header:** None</span></span>  
<span data-ttu-id="829c2-118">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="829c2-118">**Library:** None</span></span>  
<span data-ttu-id="829c2-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="829c2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="829c2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="829c2-120">See also</span></span>

- [<span data-ttu-id="829c2-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="829c2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="829c2-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="829c2-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
