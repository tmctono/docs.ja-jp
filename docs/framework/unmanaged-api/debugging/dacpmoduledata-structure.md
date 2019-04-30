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
ms.openlocfilehash: 752d87c5f4a6b8d854a06be8962ee754cdd4622d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965959"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="8e6a8-102">DacpModuleData 構造体</span><span class="sxs-lookup"><span data-stu-id="8e6a8-102">DacpModuleData Structure</span></span>

<span data-ttu-id="8e6a8-103">トランスポートのバッファーをモジュールのランタイム情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8e6a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e6a8-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="8e6a8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8e6a8-105">Members</span></span>

| <span data-ttu-id="8e6a8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8e6a8-106">Member</span></span>    | <span data-ttu-id="8e6a8-107">説明</span><span class="sxs-lookup"><span data-stu-id="8e6a8-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="8e6a8-108">モジュール オブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="8e6a8-109">ポータブル実行可能 (PE) ファイルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="8e6a8-110">読み込まれたイメージのアドレスの基本です。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="8e6a8-111">その他のモジュールについては、ランタイムによって使用されるペイロードのバッファー。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8e6a8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e6a8-112">Remarks</span></span>

<span data-ttu-id="8e6a8-113">この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8e6a8-114">これを使用するには、上で指定した構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e6a8-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e6a8-115">Requirements</span></span>
<span data-ttu-id="8e6a8-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e6a8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8e6a8-117">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="8e6a8-117">**Header:** None</span></span>  
<span data-ttu-id="8e6a8-118">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="8e6a8-118">**Library:** None</span></span>  
<span data-ttu-id="8e6a8-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e6a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e6a8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e6a8-120">See also</span></span>

- [<span data-ttu-id="8e6a8-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8e6a8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8e6a8-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="8e6a8-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
