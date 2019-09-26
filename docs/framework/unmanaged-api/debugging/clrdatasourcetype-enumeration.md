---
title: CLRDataSourceType 列挙型
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274092"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="9ef1a-102">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="9ef1a-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="9ef1a-103">CLRDATA_IL_ADDRESS_MAP 構造体によって使用される値を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ef1a-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9ef1a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ef1a-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="9ef1a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9ef1a-105">Members</span></span>

| <span data-ttu-id="9ef1a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9ef1a-106">Member</span></span>                        | <span data-ttu-id="9ef1a-107">説明</span><span class="sxs-lookup"><span data-stu-id="9ef1a-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="9ef1a-108">他に何も適用されないことを示すには</span><span class="sxs-lookup"><span data-stu-id="9ef1a-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="9ef1a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="9ef1a-109">Remarks</span></span>

<span data-ttu-id="9ef1a-110">この列挙体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9ef1a-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9ef1a-111">これを使用するには、コードで前述したように、列挙型を定義します。</span><span class="sxs-lookup"><span data-stu-id="9ef1a-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="9ef1a-112">これは、「 `CLRDATA_ENUM` [Common Data Types](../common-data-types-unmanaged-api-reference.md)」で説明されているように、という別名でもあります。</span><span class="sxs-lookup"><span data-stu-id="9ef1a-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9ef1a-113">要件</span><span class="sxs-lookup"><span data-stu-id="9ef1a-113">Requirements</span></span>

<span data-ttu-id="9ef1a-114">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef1a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9ef1a-115">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="9ef1a-115">**Header:** None</span></span>  
<span data-ttu-id="9ef1a-116">**ライブラリ**なし</span><span class="sxs-lookup"><span data-stu-id="9ef1a-116">**Library:** None</span></span>  
<span data-ttu-id="9ef1a-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ef1a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ef1a-118">See also</span></span>

- [<span data-ttu-id="9ef1a-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9ef1a-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="9ef1a-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="9ef1a-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
