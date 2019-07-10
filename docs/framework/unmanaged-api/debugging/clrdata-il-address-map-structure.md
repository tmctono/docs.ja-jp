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
ms.openlocfilehash: 2f34ae3e6687027aeb75e7ea169487fc8cbda466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741033"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="be231-102">CLRDATA_IL_ADDRESS_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="be231-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="be231-103">アドレスのマッピングには、IL を定義します。</span><span class="sxs-lookup"><span data-stu-id="be231-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="be231-104">構文</span><span class="sxs-lookup"><span data-stu-id="be231-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="be231-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="be231-105">Members</span></span>

| <span data-ttu-id="be231-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="be231-106">Member</span></span>         | <span data-ttu-id="be231-107">説明</span><span class="sxs-lookup"><span data-stu-id="be231-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="be231-108">含まれているアドレスの範囲の IL オフセット</span><span class="sxs-lookup"><span data-stu-id="be231-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="be231-109">範囲の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="be231-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="be231-110">範囲の終了アドレス。</span><span class="sxs-lookup"><span data-stu-id="be231-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="be231-111">データの型。</span><span class="sxs-lookup"><span data-stu-id="be231-111">The type of the data.</span></span> <span data-ttu-id="be231-112">この値が使用されません。</span><span class="sxs-lookup"><span data-stu-id="be231-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="be231-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="be231-113">Remarks</span></span>

<span data-ttu-id="be231-114">この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="be231-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="be231-115">これを使用する構造を定義、上で指定した場所`CLRDATA_ADDRESS`は 64 ビット符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="be231-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="be231-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="be231-116">Requirements</span></span>

<span data-ttu-id="be231-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be231-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="be231-118">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="be231-118">**Header:** None</span></span>  
<span data-ttu-id="be231-119">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="be231-119">**Library:** None</span></span>   
<span data-ttu-id="be231-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="be231-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="be231-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="be231-121">See also</span></span>

- [<span data-ttu-id="be231-122">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="be231-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="be231-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="be231-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="be231-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="be231-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
