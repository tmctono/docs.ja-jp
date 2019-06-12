---
title: CorDebugGuidToTypeMapping 構造体
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025990"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="02c62-102">CorDebugGuidToTypeMapping 構造体</span><span class="sxs-lookup"><span data-stu-id="02c62-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="02c62-103">Windows ランタイムの GUID を対応する ICorDebugType オブジェクトにマップします。</span><span class="sxs-lookup"><span data-stu-id="02c62-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c62-104">構文</span><span class="sxs-lookup"><span data-stu-id="02c62-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="02c62-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="02c62-105">Members</span></span>  
  
|<span data-ttu-id="02c62-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="02c62-106">Member</span></span>|<span data-ttu-id="02c62-107">説明</span><span class="sxs-lookup"><span data-stu-id="02c62-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="02c62-108">キャッシュされている Windows ランタイム型の GUID です。</span><span class="sxs-lookup"><span data-stu-id="02c62-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="02c62-109">キャッシュされている型に関する情報を提供する ICorDebugType オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="02c62-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02c62-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="02c62-110">Requirements</span></span>  
 <span data-ttu-id="02c62-111">**プラットフォーム:** Windows ランタイム。</span><span class="sxs-lookup"><span data-stu-id="02c62-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="02c62-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02c62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02c62-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02c62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02c62-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c62-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="02c62-115">See also</span></span>

- [<span data-ttu-id="02c62-116">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="02c62-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="02c62-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="02c62-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
