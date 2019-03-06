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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360440"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="35376-102">CorThreadSafetyOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="35376-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="35376-103">スレッド セーフのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="35376-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="35376-104">構文</span><span class="sxs-lookup"><span data-stu-id="35376-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="35376-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="35376-105">Members</span></span>

|<span data-ttu-id="35376-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="35376-106">Member</span></span>|<span data-ttu-id="35376-107">説明</span><span class="sxs-lookup"><span data-stu-id="35376-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="35376-108">既定値です。</span><span class="sxs-lookup"><span data-stu-id="35376-108">Default value.</span></span> <span data-ttu-id="35376-109">`MDThreadSafetyOff` と同じ。</span><span class="sxs-lookup"><span data-stu-id="35376-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="35376-110">読み取り/書き込みロックを設定できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="35376-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="35376-111">読み取り/書き込みロックを設定できることを示します。</span><span class="sxs-lookup"><span data-stu-id="35376-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="35376-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="35376-112">Requirements</span></span>

<span data-ttu-id="35376-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35376-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="35376-114">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="35376-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="35376-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35376-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="35376-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="35376-116">See also</span></span>

- [<span data-ttu-id="35376-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="35376-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
