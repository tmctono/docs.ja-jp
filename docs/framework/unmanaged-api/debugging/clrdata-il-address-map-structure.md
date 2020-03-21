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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179371"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="95aa7-102">CLRDATA_IL_ADDRESS_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="95aa7-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="95aa7-103">IL からアドレスマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="95aa7-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="95aa7-104">構文</span><span class="sxs-lookup"><span data-stu-id="95aa7-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="95aa7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="95aa7-105">Members</span></span>

| <span data-ttu-id="95aa7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="95aa7-106">Member</span></span>         | <span data-ttu-id="95aa7-107">説明</span><span class="sxs-lookup"><span data-stu-id="95aa7-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="95aa7-108">含まれるアドレス範囲の IL オフセット</span><span class="sxs-lookup"><span data-stu-id="95aa7-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="95aa7-109">範囲の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="95aa7-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="95aa7-110">範囲の終了アドレス。</span><span class="sxs-lookup"><span data-stu-id="95aa7-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="95aa7-111">データの型。</span><span class="sxs-lookup"><span data-stu-id="95aa7-111">The type of the data.</span></span> <span data-ttu-id="95aa7-112">この値は現在使用されていません</span><span class="sxs-lookup"><span data-stu-id="95aa7-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="95aa7-113">解説</span><span class="sxs-lookup"><span data-stu-id="95aa7-113">Remarks</span></span>

<span data-ttu-id="95aa7-114">この構造体はランタイム内に存在し、ヘッダーやライブラリ ファイルを通じて公開されません。</span><span class="sxs-lookup"><span data-stu-id="95aa7-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="95aa7-115">これを使用するには、上記で指定した構造体を定義します`CLRDATA_ADDRESS`。</span><span class="sxs-lookup"><span data-stu-id="95aa7-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="95aa7-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="95aa7-116">Requirements</span></span>

<span data-ttu-id="95aa7-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95aa7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="95aa7-118">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="95aa7-118">**Header:** None</span></span>  
<span data-ttu-id="95aa7-119">**ライブラリ:** なし **.NET フレームワークのバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="95aa7-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="95aa7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="95aa7-120">See also</span></span>

- [<span data-ttu-id="95aa7-121">列挙型</span><span class="sxs-lookup"><span data-stu-id="95aa7-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="95aa7-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="95aa7-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="95aa7-123">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="95aa7-123">Debugging Structures</span></span>](debugging-structures.md)
