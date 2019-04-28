---
title: COR_GC_THREAD_STATS_TYPES 列挙体
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c631a0a3abb3cb2a342dfd44fdffb147b742ae3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698123"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="2b019-102">COR_GC_THREAD_STATS_TYPES 列挙体</span><span class="sxs-lookup"><span data-stu-id="2b019-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="2b019-103">スレッドのガベージ コレクションの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2b019-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b019-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b019-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="2b019-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2b019-105">Members</span></span>  
  
|<span data-ttu-id="2b019-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2b019-106">Member</span></span>|<span data-ttu-id="2b019-107">説明</span><span class="sxs-lookup"><span data-stu-id="2b019-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="2b019-108">スレッドには、最新のガベージ コレクションで昇格されたバイトがあります。</span><span class="sxs-lookup"><span data-stu-id="2b019-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b019-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b019-109">Requirements</span></span>  
 <span data-ttu-id="2b019-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b019-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b019-111">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="2b019-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2b019-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b019-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b019-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b019-113">See also</span></span>

- [<span data-ttu-id="2b019-114">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="2b019-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
