---
title: DacpGetModuleAddress 構造体
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789203"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="2c534-102">DacpGetModuleAddress 構造体</span><span class="sxs-lookup"><span data-stu-id="2c534-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="2c534-103">モジュールアドレス要求のコンテナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c534-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2c534-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c534-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="2c534-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2c534-105">Members</span></span>

| <span data-ttu-id="2c534-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2c534-106">Member</span></span>      | <span data-ttu-id="2c534-107">説明</span><span class="sxs-lookup"><span data-stu-id="2c534-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="2c534-108">モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c534-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="2c534-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="2c534-109">Methods</span></span>

| <span data-ttu-id="2c534-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="2c534-110">Method</span></span>                                                                                               | <span data-ttu-id="2c534-111">説明</span><span class="sxs-lookup"><span data-stu-id="2c534-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="2c534-112">要求</span><span class="sxs-lookup"><span data-stu-id="2c534-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="2c534-113">指定されたランタイム構造体を構造体に設定する要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c534-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2c534-114">コメント</span><span class="sxs-lookup"><span data-stu-id="2c534-114">Remarks</span></span>

<span data-ttu-id="2c534-115">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2c534-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2c534-116">これを使用するには、前に示したように構造体を定義します。 `CLRDATA_ADDRESS` は、64ビットの符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="2c534-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c534-117">要件</span><span class="sxs-lookup"><span data-stu-id="2c534-117">Requirements</span></span>
<span data-ttu-id="2c534-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c534-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2c534-119">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="2c534-119">**Header:** None</span></span>  
<span data-ttu-id="2c534-120">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="2c534-120">**Library:** None</span></span>  
<span data-ttu-id="2c534-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2c534-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2c534-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c534-122">See also</span></span>

- [<span data-ttu-id="2c534-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2c534-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="2c534-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="2c534-124">Debugging Structures</span></span>](debugging-structures.md)
