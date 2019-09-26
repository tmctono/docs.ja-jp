---
title: CLRDATA_IL_ADDRESS_MAP 構造体
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274291"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="e4a3d-102">CLRDATA_IL_ADDRESS_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="e4a3d-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="e4a3d-103">アドレスマッピングの IL を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e4a3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4a3d-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="e4a3d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e4a3d-105">Members</span></span>

| <span data-ttu-id="e4a3d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e4a3d-106">Member</span></span>         | <span data-ttu-id="e4a3d-107">説明</span><span class="sxs-lookup"><span data-stu-id="e4a3d-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="e4a3d-108">含まれているアドレス範囲の IL オフセット</span><span class="sxs-lookup"><span data-stu-id="e4a3d-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="e4a3d-109">範囲の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="e4a3d-110">範囲の終了アドレス。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="e4a3d-111">データの型。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-111">The type of the data.</span></span> <span data-ttu-id="e4a3d-112">この値は現在使用されていません</span><span class="sxs-lookup"><span data-stu-id="e4a3d-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="e4a3d-113">コメント</span><span class="sxs-lookup"><span data-stu-id="e4a3d-113">Remarks</span></span>

<span data-ttu-id="e4a3d-114">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e4a3d-115">これを使用するに`CLRDATA_ADDRESS`は、上で指定したように構造体を定義します。は、64ビットの符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4a3d-116">要件</span><span class="sxs-lookup"><span data-stu-id="e4a3d-116">Requirements</span></span>

<span data-ttu-id="e4a3d-117">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4a3d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4a3d-118">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="e4a3d-118">**Header:** None</span></span>  
<span data-ttu-id="e4a3d-119">**ライブラリ**なし</span><span class="sxs-lookup"><span data-stu-id="e4a3d-119">**Library:** None</span></span>   
<span data-ttu-id="e4a3d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4a3d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4a3d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4a3d-121">See also</span></span>

- [<span data-ttu-id="e4a3d-122">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="e4a3d-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e4a3d-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e4a3d-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="e4a3d-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="e4a3d-124">Debugging Structures</span></span>](debugging-structures.md)
