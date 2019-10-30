---
title: CLR_DEBUGGING_VERSION 構造体
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 651b916a0e3ca178432094428611f9bcc8f0fd17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132419"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="0a0b8-102">CLR_DEBUGGING_VERSION 構造体</span><span class="sxs-lookup"><span data-stu-id="0a0b8-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="0a0b8-103">デバッグのために共通言語ランタイム (CLR) の製品バージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a0b8-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="0a0b8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0a0b8-105">Members</span></span>  
  
|<span data-ttu-id="0a0b8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0a0b8-106">Member</span></span>|<span data-ttu-id="0a0b8-107">説明</span><span class="sxs-lookup"><span data-stu-id="0a0b8-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="0a0b8-108">構造体のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="0a0b8-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="0a0b8-109">メジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="0a0b8-110">マイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="0a0b8-111">ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="0a0b8-112">リビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a0b8-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a0b8-113">Remarks</span></span>  
 <span data-ttu-id="0a0b8-114">`CLR_DEBUGGING_VERSION` 構造体は COR_VERSION 構造体と同じですが、`CLR_DEBUGGING_VERSION` 構造体には、追加の構造バージョンフィールド (`wStructVersion`) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="0a0b8-115">現在、このフィールドは0に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0b8-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="0a0b8-116">Requirements</span></span>  
 <span data-ttu-id="0a0b8-117">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0b8-118">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="0a0b8-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0a0b8-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a0b8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a0b8-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0b8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a0b8-121">See also</span></span>

- [<span data-ttu-id="0a0b8-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="0a0b8-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0a0b8-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0a0b8-123">Debugging</span></span>](index.md)
