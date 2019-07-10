---
title: COR_VERSION 構造体
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f0a36d186c6d9788d43b075bf9d67c36ed1acb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740570"
---
# <a name="corversion-structure"></a><span data-ttu-id="6aa0c-102">COR_VERSION 構造体</span><span class="sxs-lookup"><span data-stu-id="6aa0c-102">COR_VERSION Structure</span></span>
<span data-ttu-id="6aa0c-103">共通言語ランタイムの標準の 4 つの部分のバージョン番号を保存します。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6aa0c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="6aa0c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6aa0c-105">Members</span></span>  
  
|<span data-ttu-id="6aa0c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6aa0c-106">Member</span></span>|<span data-ttu-id="6aa0c-107">説明</span><span class="sxs-lookup"><span data-stu-id="6aa0c-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="6aa0c-108">メジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="6aa0c-109">マイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="6aa0c-110">ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="6aa0c-111">サブ ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aa0c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aa0c-112">Remarks</span></span>  
 <span data-ttu-id="6aa0c-113">1\.0.3705.288 をバージョン番号には、1 はメジャー バージョン番号、マイナー バージョン番号が 0 には 3705 はビルド番号、および 288 はサブ ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa0c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6aa0c-114">Requirements</span></span>  
 <span data-ttu-id="6aa0c-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa0c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa0c-116">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="6aa0c-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="6aa0c-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aa0c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aa0c-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa0c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa0c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa0c-119">See also</span></span>

- [<span data-ttu-id="6aa0c-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="6aa0c-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="6aa0c-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6aa0c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
