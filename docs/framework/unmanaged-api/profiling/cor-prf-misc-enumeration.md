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
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867127"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="4ad93-102">COR_PRF_MISC 列挙型</span><span class="sxs-lookup"><span data-stu-id="4ad93-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="4ad93-103">特殊な識別子を指定する定数値を含めます。</span><span class="sxs-lookup"><span data-stu-id="4ad93-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad93-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ad93-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="4ad93-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4ad93-105">Members</span></span>  
  
|<span data-ttu-id="4ad93-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4ad93-106">Member</span></span>|<span data-ttu-id="4ad93-107">説明</span><span class="sxs-lookup"><span data-stu-id="4ad93-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="4ad93-108">アセンブリにまだアタッチされていないモジュールに対して[ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)によって使用される既定の識別子。</span><span class="sxs-lookup"><span data-stu-id="4ad93-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="4ad93-109">クラスに属していないグローバル定数の既定のクラス識別子。</span><span class="sxs-lookup"><span data-stu-id="4ad93-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="4ad93-110">モジュールに属さないグローバルオブジェクトの既定のモジュール識別子。</span><span class="sxs-lookup"><span data-stu-id="4ad93-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ad93-111">要件</span><span class="sxs-lookup"><span data-stu-id="4ad93-111">Requirements</span></span>  
 <span data-ttu-id="4ad93-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ad93-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad93-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ad93-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ad93-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ad93-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad93-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad93-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad93-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ad93-116">See also</span></span>

- [<span data-ttu-id="4ad93-117">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="4ad93-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
