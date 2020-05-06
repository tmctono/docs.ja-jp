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
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860827"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="9833b-102">DacpGetModuleAddress 構造体</span><span class="sxs-lookup"><span data-stu-id="9833b-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="9833b-103">モジュールアドレス要求のコンテナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9833b-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9833b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9833b-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="9833b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9833b-105">Members</span></span>

| <span data-ttu-id="9833b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9833b-106">Member</span></span>      | <span data-ttu-id="9833b-107">説明</span><span class="sxs-lookup"><span data-stu-id="9833b-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="9833b-108">モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9833b-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="9833b-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="9833b-109">Methods</span></span>

| <span data-ttu-id="9833b-110">Method</span><span class="sxs-lookup"><span data-stu-id="9833b-110">Method</span></span>                                                                                               | <span data-ttu-id="9833b-111">説明</span><span class="sxs-lookup"><span data-stu-id="9833b-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="9833b-112">Request</span><span class="sxs-lookup"><span data-stu-id="9833b-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="9833b-113">指定されたランタイム構造体を構造体に設定する要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="9833b-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9833b-114">解説</span><span class="sxs-lookup"><span data-stu-id="9833b-114">Remarks</span></span>

<span data-ttu-id="9833b-115">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9833b-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9833b-116">これを使用するに`CLRDATA_ADDRESS`は、上で指定したように構造体を定義します。は、64ビットの符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="9833b-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="9833b-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9833b-117">Requirements</span></span>
<span data-ttu-id="9833b-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9833b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9833b-119">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="9833b-119">**Header:** None</span></span>  
<span data-ttu-id="9833b-120">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="9833b-120">**Library:** None</span></span>  
<span data-ttu-id="9833b-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9833b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9833b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9833b-122">See also</span></span>

- [<span data-ttu-id="9833b-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9833b-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="9833b-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="9833b-124">Debugging Structures</span></span>](debugging-structures.md)
