---
title: CorThreadSafetyOptions 列挙型
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007508"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="54d32-102">CorThreadSafetyOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="54d32-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="54d32-103">スレッド セーフのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="54d32-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="54d32-104">構文</span><span class="sxs-lookup"><span data-stu-id="54d32-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="54d32-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="54d32-105">Members</span></span>

|<span data-ttu-id="54d32-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="54d32-106">Member</span></span>|<span data-ttu-id="54d32-107">説明</span><span class="sxs-lookup"><span data-stu-id="54d32-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="54d32-108">既定値です。</span><span class="sxs-lookup"><span data-stu-id="54d32-108">Default value.</span></span> <span data-ttu-id="54d32-109">`MDThreadSafetyOff` と同じ。</span><span class="sxs-lookup"><span data-stu-id="54d32-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="54d32-110">リーダー/ライターロックを設定できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="54d32-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="54d32-111">リーダー/ライターロックを設定できることを示します。</span><span class="sxs-lookup"><span data-stu-id="54d32-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="54d32-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="54d32-112">Requirements</span></span>

<span data-ttu-id="54d32-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d32-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="54d32-114">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="54d32-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="54d32-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d32-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="54d32-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="54d32-116">See also</span></span>

- [<span data-ttu-id="54d32-117">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="54d32-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
