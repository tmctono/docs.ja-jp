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
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793814"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="0e727-102">DacpReJitData 構造体</span><span class="sxs-lookup"><span data-stu-id="0e727-102">DacpReJitData Structure</span></span>

<span data-ttu-id="0e727-103">プロファイラーによってインストルメント化された特定のメソッドに関する基本情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="0e727-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0e727-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e727-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="0e727-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0e727-105">Members</span></span>

| <span data-ttu-id="0e727-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0e727-106">Member</span></span>           | <span data-ttu-id="0e727-107">説明</span><span class="sxs-lookup"><span data-stu-id="0e727-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="0e727-108">メソッドの ReJit リビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="0e727-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="0e727-109">指定されたバージョンのメソッドの ReJit インストルメンテーションの現在の状態を示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="0e727-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="0e727-110">メソッドの rejitted 実装のベースアドレス。</span><span class="sxs-lookup"><span data-stu-id="0e727-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="0e727-111">コメント</span><span class="sxs-lookup"><span data-stu-id="0e727-111">Remarks</span></span>

<span data-ttu-id="0e727-112">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0e727-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0e727-113">これを使用するには、前に示したように構造体を定義します。</span><span class="sxs-lookup"><span data-stu-id="0e727-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="0e727-114">Microsoft コンパイラを使用していない場合は、`ms_struct` パッキングを使用して構造体を定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0e727-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e727-115">要件</span><span class="sxs-lookup"><span data-stu-id="0e727-115">Requirements</span></span>
<span data-ttu-id="0e727-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e727-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0e727-117">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="0e727-117">**Header:** None</span></span>  
<span data-ttu-id="0e727-118">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="0e727-118">**Library:** None</span></span>  
<span data-ttu-id="0e727-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e727-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0e727-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e727-120">See also</span></span>

- [<span data-ttu-id="0e727-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0e727-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="0e727-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="0e727-122">Debugging Structures</span></span>](debugging-structures.md)
