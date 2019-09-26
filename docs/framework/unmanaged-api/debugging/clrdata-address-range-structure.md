---
title: CLRDATA_ADDRESS_RANGE 構造体
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274310"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="3c434-102">CLRDATA_ADDRESS_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="3c434-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="3c434-103">アドレス範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="3c434-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3c434-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c434-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="3c434-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3c434-105">Members</span></span>

| <span data-ttu-id="3c434-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3c434-106">Member</span></span>         | <span data-ttu-id="3c434-107">説明</span><span class="sxs-lookup"><span data-stu-id="3c434-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="3c434-108">範囲の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="3c434-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="3c434-109">範囲の終了アドレス。</span><span class="sxs-lookup"><span data-stu-id="3c434-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="3c434-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3c434-110">Remarks</span></span>

<span data-ttu-id="3c434-111">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3c434-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3c434-112">これを使用するに`CLRDATA_ADDRESS`は、上で指定したように構造体を定義します。は、64ビットの符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="3c434-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c434-113">要件</span><span class="sxs-lookup"><span data-stu-id="3c434-113">Requirements</span></span>

<span data-ttu-id="3c434-114">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c434-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3c434-115">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="3c434-115">**Header:** None</span></span>  
<span data-ttu-id="3c434-116">**ライブラリ**なし</span><span class="sxs-lookup"><span data-stu-id="3c434-116">**Library:** None</span></span>  
<span data-ttu-id="3c434-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c434-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3c434-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c434-118">See also</span></span>

- [<span data-ttu-id="3c434-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3c434-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="3c434-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="3c434-120">Debugging Structures</span></span>](debugging-structures.md)
