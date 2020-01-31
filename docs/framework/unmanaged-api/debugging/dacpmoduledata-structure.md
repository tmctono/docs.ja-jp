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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793810"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="e16cd-102">DacpModuleData 構造体</span><span class="sxs-lookup"><span data-stu-id="e16cd-102">DacpModuleData Structure</span></span>

<span data-ttu-id="e16cd-103">モジュールのランタイム情報のトランスポートバッファーを定義します。</span><span class="sxs-lookup"><span data-stu-id="e16cd-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e16cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="e16cd-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="e16cd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e16cd-105">Members</span></span>

| <span data-ttu-id="e16cd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e16cd-106">Member</span></span>    | <span data-ttu-id="e16cd-107">説明</span><span class="sxs-lookup"><span data-stu-id="e16cd-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="e16cd-108">モジュールオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="e16cd-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="e16cd-109">ポータブル実行可能 (PE) ファイルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e16cd-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="e16cd-110">読み込まれたイメージのベースのアドレス。</span><span class="sxs-lookup"><span data-stu-id="e16cd-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="e16cd-111">ランタイムによって使用される追加のモジュール情報のペイロードバッファー。</span><span class="sxs-lookup"><span data-stu-id="e16cd-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e16cd-112">コメント</span><span class="sxs-lookup"><span data-stu-id="e16cd-112">Remarks</span></span>

<span data-ttu-id="e16cd-113">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e16cd-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e16cd-114">これを使用するには、前に示したように構造体を定義します。</span><span class="sxs-lookup"><span data-stu-id="e16cd-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="e16cd-115">要件</span><span class="sxs-lookup"><span data-stu-id="e16cd-115">Requirements</span></span>
<span data-ttu-id="e16cd-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e16cd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e16cd-117">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="e16cd-117">**Header:** None</span></span>  
<span data-ttu-id="e16cd-118">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="e16cd-118">**Library:** None</span></span>  
<span data-ttu-id="e16cd-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e16cd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e16cd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e16cd-120">See also</span></span>

- [<span data-ttu-id="e16cd-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e16cd-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e16cd-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="e16cd-122">Debugging Structures</span></span>](debugging-structures.md)
