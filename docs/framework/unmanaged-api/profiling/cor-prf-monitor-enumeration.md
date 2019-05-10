---
title: COR_PRF_MONITOR 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c364d4ffec4cc6958051b51583ecdaff46ff133
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621379"
---
# <a name="corprfmonitor-enumeration"></a><span data-ttu-id="96c13-102">COR_PRF_MONITOR 列挙型</span><span class="sxs-lookup"><span data-stu-id="96c13-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="96c13-103">プロファイラーがサブスクライブしようとする動作、機能、またはイベントの指定で使用する値を含めます。</span><span class="sxs-lookup"><span data-stu-id="96c13-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c13-104">構文</span><span class="sxs-lookup"><span data-stu-id="96c13-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="96c13-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-105">Members</span></span>  
 <span data-ttu-id="96c13-106">次のセクションでは一覧`COR_PRF_MONITOR`カテゴリ別の列挙型メンバー。</span><span class="sxs-lookup"><span data-stu-id="96c13-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="96c13-107">カテゴリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96c13-107">The categories are:</span></span>  
  
- [<span data-ttu-id="96c13-108">フラグが設定されていません</span><span class="sxs-lookup"><span data-stu-id="96c13-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="96c13-109">コールバック フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="96c13-110">機能の有効化フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="96c13-111">構成フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="96c13-112">複合フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a><span data-ttu-id="96c13-113">フラグが設定されていません</span><span class="sxs-lookup"><span data-stu-id="96c13-113">No flags set</span></span>  
  
|<span data-ttu-id="96c13-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-114">Member</span></span>|<span data-ttu-id="96c13-115">説明</span><span class="sxs-lookup"><span data-stu-id="96c13-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="96c13-116">フラグが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="96c13-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a><span data-ttu-id="96c13-117">コールバック フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-117">Callback flags</span></span>  
  
|<span data-ttu-id="96c13-118">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-118">Member</span></span>|<span data-ttu-id="96c13-119">説明</span><span class="sxs-lookup"><span data-stu-id="96c13-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="96c13-120">すべてのコールバック イベントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="96c13-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="96c13-121">コントロール、`AppDomainCreation*`と`AppDomainShutdown*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="96c13-122">コントロール、`AssemblyLoad*`と`AssemblyUnload*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="96c13-123">コントロール、`JITCachedFunctionSearch*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="96c13-124">このフラグの動作は、.NET Framework バージョン 2.0 で変更されています。</span><span class="sxs-lookup"><span data-stu-id="96c13-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="96c13-125">コントロール、`COMClassicVTable*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="96c13-126">コントロール、`ClassLoad*`と`ClassUnload*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="96c13-127">コントロール、`ExceptionCLRCatcher*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="96c13-128">コントロール、 [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)と[ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96c13-128">Controls the [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="96c13-129">コントロール、 `FunctionEnter*`、 `FunctionLeave*`、および`FunctionTailCall*`[プロファイリング グローバル静的関数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c13-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="96c13-130">コントロール、 [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)コールバックと`ExceptionSearch*`、 `ExceptionOSHandler*`、 `ExceptionUnwind*`、および`ExceptionCatcher*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-130">Controls the [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="96c13-131">コントロール、 [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-131">Controls the [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="96c13-132">コントロール、 [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)、 [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)、 [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)、 [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)、 [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)、 [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)、 [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)、 [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)、 [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)、 [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)、 [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)、 [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)、および[FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)コールバックで、`ICorProfilerCallback*`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-132">Controls the [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="96c13-133">コントロール、 `JITCompilation*`、 [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)、および[JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-133">Controls the `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="96c13-134">コントロール、 `ModuleLoad*`、 `ModuleUnload*`、および[ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-134">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="96c13-135">コントロール、 [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-135">Controls the [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="96c13-136">コントロール、`Remoting*`コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-136">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="96c13-137">`Remoting*` コールバックが非同期イベントを監視するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="96c13-137">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="96c13-138">クッキーが `Remoting*` コールバックに渡されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="96c13-138">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="96c13-139">コントロール、 `RuntimeSuspend*`、 `RuntimeResume*`、 [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)、および[RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)コールバックで、 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-139">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="96c13-140">コントロール、 [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)、 [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)、 [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)、および[ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)コールバックで、[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)と[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="96c13-140">Controls the [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a><span data-ttu-id="96c13-141">機能の有効化フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-141">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="96c13-142">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-142">Member</span></span>|<span data-ttu-id="96c13-143">説明</span><span class="sxs-lookup"><span data-stu-id="96c13-143">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="96c13-144">正確な取得できるように`ClassID`ジェネリック関数を呼び出して、 [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)メソッドを`COR_PRF_FRAME_INFO`によって返される値、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="96c13-144">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="96c13-145">により引数のトレースを使用して、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)コールバックまたは[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)コールバックと[GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="96c13-145">Enables argument tracing using the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback or the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="96c13-146">戻り値を使用してトレースを有効、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)コールバックまたは[FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)コールバックと[GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="96c13-146">Enables tracing of return values by using the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback or the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="96c13-147">非推奨。</span><span class="sxs-lookup"><span data-stu-id="96c13-147">Deprecated.</span></span><br /><br /> <span data-ttu-id="96c13-148">プロセス中のデバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96c13-148">In process debugging is not supported.</span></span> <span data-ttu-id="96c13-149">このフラグは無効です。</span><span class="sxs-lookup"><span data-stu-id="96c13-149">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="96c13-150">非推奨。</span><span class="sxs-lookup"><span data-stu-id="96c13-150">Deprecated.</span></span><br /><br /> <span data-ttu-id="96c13-151">により、プロファイラーを使用して IL からネイティブへのマップを取得する[GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c13-151">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="96c13-152">.NET Framework 2.0 以降、ランタイムは常に IL-to-native マップを追跡するため、このフラグは常に設定されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="96c13-152">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="96c13-153">プロファイラーがオブジェクトの割り当て通知を必要とする可能性があることをランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="96c13-153">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="96c13-154">このフラグは、初期化中に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c13-154">This flag must be set during initialization.</span></span> <span data-ttu-id="96c13-155">これにより、プロファイラーを使用して、その後、`COR_PRF_MONITOR_OBJECT_ALLOCATED`フラグを受け取る[ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="96c13-155">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="96c13-156">呼び出しを有効に、 [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)と[RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="96c13-156">Enables calls to the [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="96c13-157">プロファイラーは起動時にこのフラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c13-157">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="96c13-158">プロファイラーがこのフラグを設定する場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c13-158">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="96c13-159">呼び出しを有効に、 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="96c13-159">Enables calls to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a><span data-ttu-id="96c13-160">構成フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-160">Configuration flags</span></span>  
  
|<span data-ttu-id="96c13-161">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-161">Member</span></span>|<span data-ttu-id="96c13-162">説明</span><span class="sxs-lookup"><span data-stu-id="96c13-162">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="96c13-163">(プロファイラーが拡張したイメージも含めて) すべてのネイティブ イメージがロードされないようにします。</span><span class="sxs-lookup"><span data-stu-id="96c13-163">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="96c13-164">このフラグと `COR_PRF_USE_PROFILE_IMAGES` フラグが両方指定されている場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="96c13-164">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="96c13-165">すべてのインライン展開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="96c13-165">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="96c13-166">すべてのコードの最適化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="96c13-166">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="96c13-167">セキュリティの透過性チェックを無効にします。このチェックは通常 just-in-time (JIT) コンパイル中に行われ、完全に信頼されているアセンブリではクラスのロード中に行われます。</span><span class="sxs-lookup"><span data-stu-id="96c13-167">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="96c13-168">これにより、いくつかのインストルメンテーションの実行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="96c13-168">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="96c13-169">ネイティブ イメージを検索して、プロファイラーが拡張したイメージを見つけます。</span><span class="sxs-lookup"><span data-stu-id="96c13-169">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="96c13-170">特定のアセンブリでプロファイラーが拡張したイメージが見つからなかった場合、共通言語ランタイムはそのアセンブリの JIT に戻ります。</span><span class="sxs-lookup"><span data-stu-id="96c13-170">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="96c13-171">このフラグと `COR_PRF_DISABLE_ALL_NGEN_IMAGES` フラグが両方指定されている場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="96c13-171">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a><span data-ttu-id="96c13-172">複合フラグ</span><span class="sxs-lookup"><span data-stu-id="96c13-172">Composite flags</span></span>  
  
|<span data-ttu-id="96c13-173">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c13-173">Member</span></span>|<span data-ttu-id="96c13-174">説明</span><span class="sxs-lookup"><span data-stu-id="96c13-174">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="96c13-175">`COR_PRF_MONITOR` のすべてのフラグ値を表します。</span><span class="sxs-lookup"><span data-stu-id="96c13-175">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="96c13-176">プロファイラーが実行中のアプリケーションに割り当てられた後に設定することが可能な、`COR_PRF_MONITOR` のすべてのフラグを表します。</span><span class="sxs-lookup"><span data-stu-id="96c13-176">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="96c13-177">構文セクションは、このビットマスク内に存在する個々のフラグを示します。</span><span class="sxs-lookup"><span data-stu-id="96c13-177">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="96c13-178">すべてのコールバック イベントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="96c13-178">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="96c13-179">初期化中にのみ設定可能な、`COR_PRF_MONITOR` のすべてのフラグを表します。</span><span class="sxs-lookup"><span data-stu-id="96c13-179">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="96c13-180">初期化の後にこれらのいずれかのフラグを変更しようとすると、処理が失敗したことを示す `HRESULT` 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="96c13-180">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="96c13-181">プロファイルが強化されたイメージを必要とするすべての `COR_PRF_MONITOR` フラグを表しています。</span><span class="sxs-lookup"><span data-stu-id="96c13-181">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96c13-182">Remarks</span><span class="sxs-lookup"><span data-stu-id="96c13-182">Remarks</span></span>  
 <span data-ttu-id="96c13-183">A`COR_PRF_MONITOR`で値が使用される、 [icorprofilerinfo::geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)と[icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)イベント通知を発行する共通言語ランタイムを定義する方法プロファイラー。</span><span class="sxs-lookup"><span data-stu-id="96c13-183">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c13-184">必要条件</span><span class="sxs-lookup"><span data-stu-id="96c13-184">Requirements</span></span>  
 <span data-ttu-id="96c13-185">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c13-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96c13-186">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96c13-186">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96c13-187">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96c13-187">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96c13-188">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c13-188">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c13-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="96c13-189">See also</span></span>

- [<span data-ttu-id="96c13-190">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="96c13-190">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="96c13-191">GetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="96c13-191">GetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="96c13-192">SetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="96c13-192">SetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
