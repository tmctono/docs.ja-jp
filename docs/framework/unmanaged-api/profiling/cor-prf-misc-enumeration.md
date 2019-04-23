---
title: COR_PRF_MISC 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199493"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="bb61c-102">COR_PRF_MISC 列挙型</span><span class="sxs-lookup"><span data-stu-id="bb61c-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="bb61c-103">特殊な識別子を指定する定数値を含めます。</span><span class="sxs-lookup"><span data-stu-id="bb61c-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb61c-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb61c-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="bb61c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bb61c-105">Members</span></span>  
  
|<span data-ttu-id="bb61c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bb61c-106">Member</span></span>|<span data-ttu-id="bb61c-107">説明</span><span class="sxs-lookup"><span data-stu-id="bb61c-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="bb61c-108">使用される既定の識別子[icorprofilerinfo::getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)モジュールのアセンブリに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="bb61c-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="bb61c-109">クラスに属していないグローバル定数の既定のクラス id。</span><span class="sxs-lookup"><span data-stu-id="bb61c-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="bb61c-110">モジュールに属していないグローバル オブジェクトの既定のモジュール識別子。</span><span class="sxs-lookup"><span data-stu-id="bb61c-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb61c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb61c-111">Requirements</span></span>  
 <span data-ttu-id="bb61c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb61c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb61c-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb61c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb61c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb61c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb61c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb61c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb61c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb61c-116">See also</span></span>

- [<span data-ttu-id="bb61c-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="bb61c-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
