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
ms.openlocfilehash: b6c3dc78b9c503747c7a2d404706eb797790b931
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175201"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="2d80e-102">COR_PRF_MONITOR 列挙型</span><span class="sxs-lookup"><span data-stu-id="2d80e-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="2d80e-103">プロファイラーがサブスクライブしようとする動作、機能、またはイベントの指定で使用する値を含めます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d80e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d80e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="2d80e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-105">Members</span></span>  
 <span data-ttu-id="2d80e-106">次のセクションでは`COR_PRF_MONITOR`、カテゴリ別の列挙メンバーを示します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="2d80e-107">カテゴリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d80e-107">The categories are:</span></span>  
  
- [<span data-ttu-id="2d80e-108">フラグが設定されていない</span><span class="sxs-lookup"><span data-stu-id="2d80e-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="2d80e-109">コールバック フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="2d80e-110">機能の有効化フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="2d80e-111">構成フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="2d80e-112">複合フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a><span data-ttu-id="2d80e-113">フラグの設定なし</span><span class="sxs-lookup"><span data-stu-id="2d80e-113">No flags set</span></span>  
  
|<span data-ttu-id="2d80e-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-114">Member</span></span>|<span data-ttu-id="2d80e-115">説明</span><span class="sxs-lookup"><span data-stu-id="2d80e-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="2d80e-116">フラグが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="2d80e-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a><span data-ttu-id="2d80e-117">コールバック フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-117">Callback flags</span></span>  
  
|<span data-ttu-id="2d80e-118">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-118">Member</span></span>|<span data-ttu-id="2d80e-119">説明</span><span class="sxs-lookup"><span data-stu-id="2d80e-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="2d80e-120">すべてのコールバック イベントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="2d80e-121">インターフェイスの`AppDomainCreation*`コールバック`AppDomainShutdown*`と[コールバック](icorprofilercallback-interface.md)を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="2d80e-122">インターフェイスの`AssemblyLoad*`コールバック`AssemblyUnload*`と[コールバック](icorprofilercallback-interface.md)を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="2d80e-123">インターフェイス内`JITCachedFunctionSearch*`のコールバック[を](icorprofilercallback-interface.md)制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="2d80e-124">このフラグの動作は、.NET Framework バージョン 2.0 で変更されています。</span><span class="sxs-lookup"><span data-stu-id="2d80e-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="2d80e-125">インターフェイス内`COMClassicVTable*`のコールバック[を](icorprofilercallback-interface.md)制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="2d80e-126">インターフェイスの`ClassLoad*`コールバック`ClassUnload*`と[コールバック](icorprofilercallback-interface.md)を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="2d80e-127">インターフェイス内`ExceptionCLRCatcher*`のコールバック[を](icorprofilercallback-interface.md)制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="2d80e-128">[インターフェイス](icorprofilercallback-interface.md)の[コールバック](icorprofilercallback-unmanagedtomanagedtransition-method.md)を制御します。 [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)</span><span class="sxs-lookup"><span data-stu-id="2d80e-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="2d80e-129">グローバル静的`FunctionEnter*`関数`FunctionLeave*`、 `FunctionTailCall*`、 、 および[プロファイリングのグローバル静的関数](profiling-global-static-functions.md)を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="2d80e-130">[インターフェイス](icorprofilercallback-interface.md)内の[例外スロー](icorprofilercallback-exceptionthrown-method.md)コールバック`ExceptionSearch*`と`ExceptionOSHandler*``ExceptionCatcher*` `ExceptionUnwind*`、、、、、およびコールバックを制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="2d80e-131">[インターフェイス](icorprofilercallback-interface.md)の[コールバックを制御](icorprofilercallback-functionunloadstarted-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="2d80e-132">インターフェイス内の[ガベージコレクション開始](icorprofilercallback2-garbagecollectionstarted-method.md)、[ガベージコレクション終了](icorprofilercallback2-garbagecollectionfinished-method.md)、[移動参照](icorprofilercallback-movedreferences-method.md)、[移動参照2、](icorprofilercallback4-movedreferences2-method.md)[生存参照](icorprofilercallback2-survivingreferences-method.md)、[生存参照2、](icorprofilercallback4-survivingreferences2-method.md)[オブジェクト参照](icorprofilercallback-objectreferences-method.md)、[オブジェクト割り当て済みクラス](icorprofilercallback-objectsallocatedbyclass-method.md)、[ルート参照](icorprofilercallback-rootreferences-method.md)、[ルート参照2、](icorprofilercallback2-rootreferences2-method.md)[ハンドル作成](icorprofilercallback2-handlecreated-method.md)、[ハンドル破棄](icorprofilercallback2-handledestroyed-method.md)、[および終了可能なオブジェクトキュー](icorprofilercallback2-finalizeableobjectqueued-method.md)コールバック`ICorProfilerCallback*`を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="2d80e-133">割`COR_PRF_MONITOR_GC`り当てられると、同時実行ガベージ コレクションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="2d80e-134">インターフェイス内`JITCompilation*`のコールバック[、JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)、および[JITInlining](icorprofilercallback-jitinlining-method.md) [コールバック](icorprofilercallback-interface.md)を制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="2d80e-135">インターフェイスの`ModuleLoad*`コールバック`ModuleUnload*`、、および[モジュールアタッチト アセンブリ](icorprofilercallback-moduleattachedtoassembly-method.md)[ICorProfilerCallback](icorprofilercallback-interface.md)コールバックを制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="2d80e-136">[インターフェイス内](icorprofilercallback-interface.md)の[オブジェクト割り当て](icorprofilercallback-objectallocated-method.md)コールバックを制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="2d80e-137">インターフェイス内`Remoting*`のコールバック[を](icorprofilercallback-interface.md)制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="2d80e-138">`Remoting*` コールバックが非同期イベントを監視するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="2d80e-139">クッキーが `Remoting*` コールバックに渡されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="2d80e-140">インターフェイス内`RuntimeSuspend*`の`RuntimeResume*`コールバック 、ランタイム[スレッドの中断](icorprofilercallback-runtimethreadsuspended-method.md)、および[ランタイム スレッド再開コールバック](icorprofilercallback-runtimethreadresumed-method.md)[を制御](icorprofilercallback-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="2d80e-141">インターフェイスで[スレッド作成](icorprofilercallback-threadcreated-method.md)、[スレッド破棄](icorprofilercallback-threaddestroyed-method.md)、[スレッド割り当てToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)、および[スレッド名を変更した](icorprofilercallback2-threadnamechanged-method.md)[コールバックを制御](icorprofilercallback-interface.md)します[。](icorprofilercallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="2d80e-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a><span data-ttu-id="2d80e-142">機能の有効化フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="2d80e-143">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-143">Member</span></span>|<span data-ttu-id="2d80e-144">説明</span><span class="sxs-lookup"><span data-stu-id="2d80e-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="2d80e-145">[FunctionEnter2](functionenter2-function.md)コールバックによって`ClassID`返される値を使用して[GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)メソッドを`COR_PRF_FRAME_INFO`呼び出すことによって、ジェネリック関数の正確な取得を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="2d80e-146">[関数のコールバックまたは関数を](functionenter2-function.md)使用して引数[トレースを有効](functionenter3withinfo-function.md)にします。 [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)</span><span class="sxs-lookup"><span data-stu-id="2d80e-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="2d80e-147">[コールバックまたは関数](functionleave2-function.md)[Leave3WithInfo](functionleave3withinfo-function.md)コールバックと[GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)メソッドを使用して戻り値のトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="2d80e-148">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="2d80e-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="2d80e-149">プロセス中のデバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2d80e-149">In process debugging is not supported.</span></span> <span data-ttu-id="2d80e-150">このフラグは無効です。</span><span class="sxs-lookup"><span data-stu-id="2d80e-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="2d80e-151">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="2d80e-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="2d80e-152">プロファイラーが[GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)を使用して IL からネイティブへのマップを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="2d80e-153">.NET Framework 2.0 以降、ランタイムは常に IL-to-native マップを追跡するため、このフラグは常に設定されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="2d80e-154">プロファイラーがオブジェクトの割り当て通知を必要とする可能性があることをランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="2d80e-155">このフラグは、初期化中に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-155">This flag must be set during initialization.</span></span> <span data-ttu-id="2d80e-156">このオプションを使用すると、プロファイラー`COR_PRF_MONITOR_OBJECT_ALLOCATED`は、後でフラグを使用して[ObjectAllocated](icorprofilercallback-objectallocated-method.md)コールバックを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="2d80e-157">[メソッドの呼](icorprofilerinfo4-requestrejit-method.md)び出しを有効[にします](icorprofilerinfo4-requestrevert-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2d80e-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="2d80e-158">プロファイラーは起動時にこのフラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="2d80e-159">プロファイラーがこのフラグを設定する場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="2d80e-160">[メソッド](icorprofilerinfo2-dostacksnapshot-method.md)の呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a><span data-ttu-id="2d80e-161">構成フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-161">Configuration flags</span></span>  
  
|<span data-ttu-id="2d80e-162">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-162">Member</span></span>|<span data-ttu-id="2d80e-163">説明</span><span class="sxs-lookup"><span data-stu-id="2d80e-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="2d80e-164">(プロファイラーが拡張したイメージも含めて) すべてのネイティブ イメージがロードされないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="2d80e-165">このフラグと `COR_PRF_USE_PROFILE_IMAGES` フラグが両方指定されている場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="2d80e-166">すべてのインライン展開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="2d80e-167">すべてのコードの最適化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="2d80e-168">セキュリティの透過性チェックを無効にします。このチェックは通常 just-in-time (JIT) コンパイル中に行われ、完全に信頼されているアセンブリではクラスのロード中に行われます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="2d80e-169">これにより、いくつかのインストルメンテーションの実行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="2d80e-170">ネイティブ イメージを検索して、プロファイラーが拡張したイメージを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="2d80e-171">特定のアセンブリでプロファイラーが拡張したイメージが見つからなかった場合、共通言語ランタイムはそのアセンブリの JIT に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2d80e-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="2d80e-172">このフラグと `COR_PRF_DISABLE_ALL_NGEN_IMAGES` フラグが両方指定されている場合は、`COR_PRF_DISABLE_ALL_NGEN_IMAGES` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a><span data-ttu-id="2d80e-173">複合フラグ</span><span class="sxs-lookup"><span data-stu-id="2d80e-173">Composite flags</span></span>  
  
|<span data-ttu-id="2d80e-174">メンバー</span><span class="sxs-lookup"><span data-stu-id="2d80e-174">Member</span></span>|<span data-ttu-id="2d80e-175">説明</span><span class="sxs-lookup"><span data-stu-id="2d80e-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="2d80e-176">`COR_PRF_MONITOR` のすべてのフラグ値を表します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="2d80e-177">プロファイラーが実行中のアプリケーションに割り当てられた後に設定することが可能な、`COR_PRF_MONITOR` のすべてのフラグを表します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="2d80e-178">構文セクションは、このビットマスク内に存在する個々のフラグを示します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="2d80e-179">すべてのコールバック イベントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d80e-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="2d80e-180">初期化中にのみ設定可能な、`COR_PRF_MONITOR` のすべてのフラグを表します。</span><span class="sxs-lookup"><span data-stu-id="2d80e-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="2d80e-181">初期化の後にこれらのいずれかのフラグを変更しようとすると、処理が失敗したことを示す `HRESULT` 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="2d80e-182">プロファイルが強化されたイメージを必要とするすべての `COR_PRF_MONITOR` フラグを表しています。</span><span class="sxs-lookup"><span data-stu-id="2d80e-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d80e-183">解説</span><span class="sxs-lookup"><span data-stu-id="2d80e-183">Remarks</span></span>  
 <span data-ttu-id="2d80e-184">`COR_PRF_MONITOR`値は、共通言語ランタイムがプロファイラーに対して行うイベント通知を定義するために[、ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md)および[ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)メソッドと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d80e-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d80e-185">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d80e-185">Requirements</span></span>  
 <span data-ttu-id="2d80e-186">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d80e-186">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d80e-187">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d80e-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d80e-188">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d80e-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d80e-189">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d80e-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d80e-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d80e-190">See also</span></span>

- [<span data-ttu-id="2d80e-191">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="2d80e-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="2d80e-192">GetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="2d80e-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="2d80e-193">SetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="2d80e-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
