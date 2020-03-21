---
title: DacpModuleData 構造体
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179185"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="3aa52-102">DacpModuleData 構造体</span><span class="sxs-lookup"><span data-stu-id="3aa52-102">DacpModuleData Structure</span></span>

<span data-ttu-id="3aa52-103">モジュールの実行時情報のトランスポート バッファーを定義します。</span><span class="sxs-lookup"><span data-stu-id="3aa52-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3aa52-104">構文</span><span class="sxs-lookup"><span data-stu-id="3aa52-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="3aa52-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3aa52-105">Members</span></span>

| <span data-ttu-id="3aa52-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3aa52-106">Member</span></span>    | <span data-ttu-id="3aa52-107">説明</span><span class="sxs-lookup"><span data-stu-id="3aa52-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="3aa52-108">モジュール オブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="3aa52-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="3aa52-109">ポータブル実行可能 (PE) ファイルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3aa52-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="3aa52-110">読み込まれたイメージのベースのアドレス。</span><span class="sxs-lookup"><span data-stu-id="3aa52-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="3aa52-111">ランタイムで使用される追加のモジュール情報のペイロード バッファー。</span><span class="sxs-lookup"><span data-stu-id="3aa52-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3aa52-112">解説</span><span class="sxs-lookup"><span data-stu-id="3aa52-112">Remarks</span></span>

<span data-ttu-id="3aa52-113">この構造体はランタイム内に存在し、ヘッダーやライブラリ ファイルを通じて公開されません。</span><span class="sxs-lookup"><span data-stu-id="3aa52-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3aa52-114">使用するには、上記で指定した構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="3aa52-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="3aa52-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="3aa52-115">Requirements</span></span>
<span data-ttu-id="3aa52-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa52-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3aa52-117">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="3aa52-117">**Header:** None</span></span>  
<span data-ttu-id="3aa52-118">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="3aa52-118">**Library:** None</span></span>  
<span data-ttu-id="3aa52-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa52-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3aa52-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3aa52-120">See also</span></span>

- [<span data-ttu-id="3aa52-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3aa52-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="3aa52-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="3aa52-122">Debugging Structures</span></span>](debugging-structures.md)
