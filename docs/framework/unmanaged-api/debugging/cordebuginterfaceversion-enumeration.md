---
title: CorDebugInterfaceVersion 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 5ebbbf01bc27974850c7e0bb3591b8f050fd0579
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179269"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="ab1b7-102">CorDebugInterfaceVersion 列挙型</span><span class="sxs-lookup"><span data-stu-id="ab1b7-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="ab1b7-103">インターフェイス、つまり .NET Framework のバージョン、またはインターフェイスが導入された .NET Framework のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab1b7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="ab1b7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ab1b7-105">Members</span></span>  
 <span data-ttu-id="ab1b7-106">以下の表に、各列挙値から対応するインターフェイスへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="ab1b7-107">また、インターフェイスがサポートされた .NET Framework の最初のバージョンについても記載しています。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="ab1b7-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="ab1b7-108">Member</span></span>|<span data-ttu-id="ab1b7-109">指定対象</span><span class="sxs-lookup"><span data-stu-id="ab1b7-109">Specifies</span></span>|<span data-ttu-id="ab1b7-110">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="ab1b7-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="ab1b7-111">.NET Framework のバージョンが無効。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="ab1b7-112">(すべてのサービス パックを含めて) .NET Framework のバージョンは 1.0。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="ab1b7-113">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="ab1b7-114">(すべてのサービス パックを含めて) .NET Framework のバージョンは 1.1。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="ab1b7-115">1.1</span><span class="sxs-lookup"><span data-stu-id="ab1b7-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="ab1b7-116">(すべてのサービス パックを含めて) .NET Framework のバージョンは 2.0。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="ab1b7-117">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="ab1b7-118">(すべてのサービス パックを含めて) .NET Framework のバージョンは 4。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="ab1b7-119">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="ab1b7-120">(すべてのサービス パックを含めて) .NET Framework のバージョンは 4.5。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="ab1b7-121">4.5</span><span class="sxs-lookup"><span data-stu-id="ab1b7-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="ab1b7-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ab1b7-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="ab1b7-123">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="ab1b7-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="ab1b7-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="ab1b7-125">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="ab1b7-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ab1b7-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="ab1b7-127">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="ab1b7-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="ab1b7-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="ab1b7-129">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="ab1b7-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="ab1b7-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="ab1b7-131">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="ab1b7-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="ab1b7-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="ab1b7-133">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="ab1b7-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="ab1b7-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="ab1b7-135">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="ab1b7-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ab1b7-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="ab1b7-137">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="ab1b7-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ab1b7-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="ab1b7-139">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="ab1b7-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ab1b7-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="ab1b7-141">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="ab1b7-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ab1b7-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="ab1b7-143">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="ab1b7-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="ab1b7-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="ab1b7-145">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="ab1b7-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ab1b7-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="ab1b7-147">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="ab1b7-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="ab1b7-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="ab1b7-149">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="ab1b7-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="ab1b7-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="ab1b7-151">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="ab1b7-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="ab1b7-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="ab1b7-153">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="ab1b7-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="ab1b7-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="ab1b7-155">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="ab1b7-156">を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="ab1b7-157">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="ab1b7-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="ab1b7-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="ab1b7-159">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="ab1b7-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="ab1b7-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="ab1b7-161">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="ab1b7-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="ab1b7-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="ab1b7-163">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="ab1b7-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="ab1b7-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="ab1b7-165">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="ab1b7-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="ab1b7-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="ab1b7-167">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="ab1b7-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="ab1b7-169">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="ab1b7-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="ab1b7-171">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="ab1b7-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="ab1b7-173">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="ab1b7-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="ab1b7-175">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="ab1b7-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="ab1b7-177">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="ab1b7-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="ab1b7-179">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="ab1b7-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="ab1b7-181">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="ab1b7-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="ab1b7-183">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="ab1b7-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="ab1b7-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="ab1b7-185">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="ab1b7-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="ab1b7-187">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="ab1b7-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="ab1b7-189">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="ab1b7-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="ab1b7-191">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="ab1b7-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="ab1b7-193">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="ab1b7-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="ab1b7-195">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="ab1b7-196">をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="ab1b7-197">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="ab1b7-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="ab1b7-199">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="ab1b7-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="ab1b7-201">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="ab1b7-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="ab1b7-203">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="ab1b7-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="ab1b7-205">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="ab1b7-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="ab1b7-207">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="ab1b7-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="ab1b7-209">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="ab1b7-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="ab1b7-211">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="ab1b7-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="ab1b7-213">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="ab1b7-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ab1b7-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="ab1b7-215">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="ab1b7-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="ab1b7-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="ab1b7-217">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="ab1b7-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="ab1b7-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="ab1b7-219">1.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="ab1b7-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="ab1b7-221">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="ab1b7-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="ab1b7-223">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="ab1b7-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="ab1b7-225">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="ab1b7-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="ab1b7-227">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="ab1b7-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="ab1b7-229">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="ab1b7-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="ab1b7-231">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="ab1b7-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="ab1b7-233">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="ab1b7-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="ab1b7-235">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="ab1b7-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="ab1b7-237">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="ab1b7-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="ab1b7-239">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="ab1b7-240">"2 のクラスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="ab1b7-241">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="ab1b7-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="ab1b7-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="ab1b7-243">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="ab1b7-244">"ICorDebugEval2"。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="ab1b7-245">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="ab1b7-246">"オブジェクト値2"</span><span class="sxs-lookup"><span data-stu-id="ab1b7-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="ab1b7-247">2.0</span><span class="sxs-lookup"><span data-stu-id="ab1b7-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="ab1b7-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="ab1b7-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="ab1b7-249">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="ab1b7-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="ab1b7-251">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="ab1b7-252">スタックウォーク</span><span class="sxs-lookup"><span data-stu-id="ab1b7-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="ab1b7-253">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="ab1b7-254">を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="ab1b7-255">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="ab1b7-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ab1b7-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="ab1b7-257">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="ab1b7-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="ab1b7-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="ab1b7-259">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="ab1b7-260">ICorDebugHeapValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab1b7-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="ab1b7-261">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="ab1b7-262">ICorDebugBlockingObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab1b7-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="ab1b7-263">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="ab1b7-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ab1b7-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="ab1b7-265">4</span><span class="sxs-lookup"><span data-stu-id="ab1b7-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="ab1b7-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="ab1b7-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="ab1b7-267">4.5</span><span class="sxs-lookup"><span data-stu-id="ab1b7-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="ab1b7-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="ab1b7-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="ab1b7-269">4.5</span><span class="sxs-lookup"><span data-stu-id="ab1b7-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="ab1b7-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="ab1b7-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="ab1b7-271">4.5</span><span class="sxs-lookup"><span data-stu-id="ab1b7-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="ab1b7-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="ab1b7-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="ab1b7-273">4.5</span><span class="sxs-lookup"><span data-stu-id="ab1b7-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="ab1b7-274">(すべてのサービス パックを含めて) .NET Framework のバージョンは最新バージョン。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="ab1b7-275">解説</span><span class="sxs-lookup"><span data-stu-id="ab1b7-275">Remarks</span></span>  
 <span data-ttu-id="ab1b7-276">デバッガーは、デバッガーが`CorDebugInterfaceVersion`サポートする .NET Framework の最高バージョンを指定するのには、[関数](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)の列挙を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="ab1b7-277">インターフェイス名</span><span class="sxs-lookup"><span data-stu-id="ab1b7-277">Interface Names</span></span>  
 <span data-ttu-id="ab1b7-278">デバッグ API でインターフェイス名の最後に示される数字 (`ICorDebugThread3` の "3" など) は、.NET Framework のバージョンではなく、インターフェイスのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="ab1b7-279">デバッグ API のすべてのインターフェイス名にはバージョン番号が含まれます (ただし .NET Framework バージョン 1 で導入されたインターフェイスは除きます)。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="ab1b7-280">インターフェイスのバージョン番号と .NET Framework のバージョン番号が同じでもそれは偶然の一致です。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="ab1b7-281">.NET Framework バージョン 1.0 で導入されたインターフェイスは暗黙的にすべてバージョン 1 であるため、このインターフェイスには番号が含まれません。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="ab1b7-282">.NET Framework バージョン 1.1 はバージョン 1.0 インターフェイスを使用しており、新しいデバッグ インターフェイスは導入していません。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="ab1b7-283">.NET Framework バージョン 2.0 で導入された 14 個のデバッグ インターフェイスは、バージョン 1 のそれらの論理的拡張であり、名前に "2" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="ab1b7-284">.NET Framework バージョン 3.0 および 3.5 は既存の .NET Framework 2.0 インターフェイスを使用しており、新しいインターフェイスは導入していません。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="ab1b7-285">.NET Framework 4 では、インターフェイスのバージョンが混在しています。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="ab1b7-286">たとえば、`ICorDebugThread3` および `ICorDebugThread4` は、`ICorDebugThread` インターフェイスの 3 番目および 4 番目のバージョンとして示されます。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="ab1b7-287">.NET Framework 4 では、`ICorDebugStackWalk`インターフェイスの最初のバージョンと 2 番目`ICorDebugNativeFrame`のバージョン`ICorDebugNativeFrame2`( ) も導入されています。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1b7-288">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab1b7-288">Requirements</span></span>  
 <span data-ttu-id="ab1b7-289">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab1b7-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1b7-290">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab1b7-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab1b7-291">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab1b7-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab1b7-292">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1b7-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1b7-293">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab1b7-293">See also</span></span>

- [<span data-ttu-id="ab1b7-294">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ab1b7-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
