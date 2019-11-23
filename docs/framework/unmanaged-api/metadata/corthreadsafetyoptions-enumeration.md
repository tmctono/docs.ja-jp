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
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442470"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="05c86-102">CorThreadSafetyOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="05c86-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="05c86-103">スレッド セーフのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="05c86-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="05c86-104">構文</span><span class="sxs-lookup"><span data-stu-id="05c86-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="05c86-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="05c86-105">Members</span></span>

|<span data-ttu-id="05c86-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="05c86-106">Member</span></span>|<span data-ttu-id="05c86-107">説明</span><span class="sxs-lookup"><span data-stu-id="05c86-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="05c86-108">Default value.</span><span class="sxs-lookup"><span data-stu-id="05c86-108">Default value.</span></span> <span data-ttu-id="05c86-109">`MDThreadSafetyOff` と同じ。</span><span class="sxs-lookup"><span data-stu-id="05c86-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="05c86-110">Indicates that a reader/writer lock cannot be set.</span><span class="sxs-lookup"><span data-stu-id="05c86-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="05c86-111">Indicates that a reader/writer lock can be set.</span><span class="sxs-lookup"><span data-stu-id="05c86-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="05c86-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="05c86-112">Requirements</span></span>

<span data-ttu-id="05c86-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05c86-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="05c86-114">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="05c86-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="05c86-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="05c86-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="05c86-116">See also</span></span>

- [<span data-ttu-id="05c86-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="05c86-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
