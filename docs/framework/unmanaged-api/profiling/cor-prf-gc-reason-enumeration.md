---
title: COR_PRF_GC_REASON 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196945"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="1c3b5-102">COR_PRF_GC_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="1c3b5-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="1c3b5-103">ガベージ コレクションが発生している理由を示します。</span><span class="sxs-lookup"><span data-stu-id="1c3b5-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c3b5-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="1c3b5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1c3b5-105">Members</span></span>  
  
|<span data-ttu-id="1c3b5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1c3b5-106">Member</span></span>|<span data-ttu-id="1c3b5-107">説明</span><span class="sxs-lookup"><span data-stu-id="1c3b5-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="1c3b5-108">ガベージ コレクションが発生しました。 によって、<xref:System.GC.Collect%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1c3b5-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="1c3b5-109">理由は、指定されていません。</span><span class="sxs-lookup"><span data-stu-id="1c3b5-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c3b5-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c3b5-110">Requirements</span></span>  
 <span data-ttu-id="1c3b5-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c3b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c3b5-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c3b5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c3b5-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c3b5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c3b5-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c3b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3b5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c3b5-115">See also</span></span>

- [<span data-ttu-id="1c3b5-116">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="1c3b5-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
