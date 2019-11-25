---
title: 相互運用 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5db68cdce0db4f8f4d85e9d1dd03720bf235d865
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974933"
---
# <a name="interop-etw-events"></a><span data-ttu-id="7e452-102">相互運用 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7e452-102">Interop ETW Events</span></span>
<span data-ttu-id="7e452-103">相互運用イベントは、Microsoft intermediate language (MSIL) のスタブ生成とキャッシュに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="7e452-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  

## <a name="ilstubgenerated-event"></a><span data-ttu-id="7e452-104">ILStubGenerated イベント</span><span class="sxs-lookup"><span data-stu-id="7e452-104">ILStubGenerated Event</span></span>

<span data-ttu-id="7e452-105">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="7e452-106">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7e452-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="7e452-107">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7e452-107">Keyword for raising the event</span></span>|<span data-ttu-id="7e452-108">レベル</span><span class="sxs-lookup"><span data-stu-id="7e452-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7e452-109">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="7e452-109">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="7e452-110">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="7e452-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="7e452-111">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7e452-112">event</span><span class="sxs-lookup"><span data-stu-id="7e452-112">Event</span></span>|<span data-ttu-id="7e452-113">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7e452-113">Event ID</span></span>|<span data-ttu-id="7e452-114">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7e452-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="7e452-115">88</span><span class="sxs-lookup"><span data-stu-id="7e452-115">88</span></span>|<span data-ttu-id="7e452-116">MSIL スタブが生成された。</span><span class="sxs-lookup"><span data-stu-id="7e452-116">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="7e452-117">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-117">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7e452-118">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7e452-118">Field name</span></span>|<span data-ttu-id="7e452-119">データの種類</span><span class="sxs-lookup"><span data-stu-id="7e452-119">Data type</span></span>|<span data-ttu-id="7e452-120">説明</span><span class="sxs-lookup"><span data-stu-id="7e452-120">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7e452-121">ModuleID</span><span class="sxs-lookup"><span data-stu-id="7e452-121">ModuleID</span></span>|<span data-ttu-id="7e452-122">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7e452-122">win:UInt16</span></span>|<span data-ttu-id="7e452-123">モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="7e452-123">The module identifier.</span></span>|  
|<span data-ttu-id="7e452-124">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="7e452-124">StubMethodID</span></span>|<span data-ttu-id="7e452-125">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7e452-125">win:UInt64</span></span>|<span data-ttu-id="7e452-126">スタブのメソッド識別子。</span><span class="sxs-lookup"><span data-stu-id="7e452-126">The stub method identifier.</span></span>|  
|<span data-ttu-id="7e452-127">StubFlags</span><span class="sxs-lookup"><span data-stu-id="7e452-127">StubFlags</span></span>|<span data-ttu-id="7e452-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7e452-128">win:UInt64</span></span>|<span data-ttu-id="7e452-129">スタブのフラグ:</span><span class="sxs-lookup"><span data-stu-id="7e452-129">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="7e452-130">0x1 - 逆方向の相互運用。</span><span class="sxs-lookup"><span data-stu-id="7e452-130">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="7e452-131">0x2 - COM 相互運用。</span><span class="sxs-lookup"><span data-stu-id="7e452-131">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="7e452-132">0x4 - NGen.exe で生成されたスタブ。</span><span class="sxs-lookup"><span data-stu-id="7e452-132">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="7e452-133">0x8 - デリゲート。</span><span class="sxs-lookup"><span data-stu-id="7e452-133">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="7e452-134">0x10-可変個引数。</span><span class="sxs-lookup"><span data-stu-id="7e452-134">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="7e452-135">0x20 - アンマネージ呼び出し先。</span><span class="sxs-lookup"><span data-stu-id="7e452-135">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="7e452-136">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="7e452-136">ManagedInteropMethodToken</span></span>|<span data-ttu-id="7e452-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7e452-137">win:UInt32</span></span>|<span data-ttu-id="7e452-138">マネージド相互運用メソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="7e452-138">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-139">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="7e452-139">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="7e452-140">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-140">win:UnicodeString</span></span>|<span data-ttu-id="7e452-141">マネージド相互運用メソッドの名前空間。</span><span class="sxs-lookup"><span data-stu-id="7e452-141">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-142">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="7e452-142">ManagedInteropMethodName</span></span>|<span data-ttu-id="7e452-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-143">win:UnicodeString</span></span>|<span data-ttu-id="7e452-144">マネージド相互運用メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="7e452-144">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-145">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="7e452-145">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="7e452-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-146">win:UnicodeString</span></span>|<span data-ttu-id="7e452-147">マネージド相互運用メソッドのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="7e452-147">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-148">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="7e452-148">NativeMethodSignature</span></span>|<span data-ttu-id="7e452-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-149">win:UnicodeString</span></span>|<span data-ttu-id="7e452-150">ネイティブ メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="7e452-150">The native method signature.</span></span>|  
|<span data-ttu-id="7e452-151">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="7e452-151">StubMethodSignature</span></span>|<span data-ttu-id="7e452-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-152">win:UnicodeString</span></span>|<span data-ttu-id="7e452-153">スタブ メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="7e452-153">The stub method signature.</span></span>|  
|<span data-ttu-id="7e452-154">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="7e452-154">StubMethodILCode</span></span>|<span data-ttu-id="7e452-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-155">win:UnicodeString</span></span>|<span data-ttu-id="7e452-156">スタブ メソッドの MSIL コード。</span><span class="sxs-lookup"><span data-stu-id="7e452-156">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="7e452-157">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7e452-157">ClrInstanceID</span></span>|<span data-ttu-id="7e452-158">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7e452-158">win:UInt16</span></span>|<span data-ttu-id="7e452-159">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7e452-159">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="ilstubcachehit-event"></a><span data-ttu-id="7e452-160">ILStubCacheHit イベント</span><span class="sxs-lookup"><span data-stu-id="7e452-160">ILStubCacheHit Event</span></span>  

<span data-ttu-id="7e452-161">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-161">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7e452-162">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7e452-162">Keyword for raising the event</span></span>|<span data-ttu-id="7e452-163">レベル</span><span class="sxs-lookup"><span data-stu-id="7e452-163">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7e452-164">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="7e452-164">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="7e452-165">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="7e452-165">Informational(4)</span></span>|  
  
 <span data-ttu-id="7e452-166">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-166">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7e452-167">event</span><span class="sxs-lookup"><span data-stu-id="7e452-167">Event</span></span>|<span data-ttu-id="7e452-168">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7e452-168">Event ID</span></span>|<span data-ttu-id="7e452-169">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7e452-169">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="7e452-170">89</span><span class="sxs-lookup"><span data-stu-id="7e452-170">89</span></span>|<span data-ttu-id="7e452-171">MSIL のキャッシュにアクセスがあった。</span><span class="sxs-lookup"><span data-stu-id="7e452-171">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="7e452-172">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7e452-172">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7e452-173">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7e452-173">Field name</span></span>|<span data-ttu-id="7e452-174">データの種類</span><span class="sxs-lookup"><span data-stu-id="7e452-174">Data type</span></span>|<span data-ttu-id="7e452-175">説明</span><span class="sxs-lookup"><span data-stu-id="7e452-175">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7e452-176">ModuleID</span><span class="sxs-lookup"><span data-stu-id="7e452-176">ModuleID</span></span>|<span data-ttu-id="7e452-177">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7e452-177">win:UInt16</span></span>|<span data-ttu-id="7e452-178">モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="7e452-178">The module identifier.</span></span>|  
|<span data-ttu-id="7e452-179">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="7e452-179">StubMethodID</span></span>|<span data-ttu-id="7e452-180">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7e452-180">win:UInt64</span></span>|<span data-ttu-id="7e452-181">スタブのメソッド識別子。</span><span class="sxs-lookup"><span data-stu-id="7e452-181">The stub method identifier.</span></span>|  
|<span data-ttu-id="7e452-182">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="7e452-182">ManagedInteropMethodToken</span></span>|<span data-ttu-id="7e452-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7e452-183">win:UInt32</span></span>|<span data-ttu-id="7e452-184">マネージド相互運用メソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="7e452-184">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-185">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="7e452-185">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="7e452-186">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-186">win:UnicodeString</span></span>|<span data-ttu-id="7e452-187">マネージド相互運用メソッドの名前空間。</span><span class="sxs-lookup"><span data-stu-id="7e452-187">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-188">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="7e452-188">ManagedInteropMethodName</span></span>|<span data-ttu-id="7e452-189">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-189">win:UnicodeString</span></span>|<span data-ttu-id="7e452-190">マネージド相互運用メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="7e452-190">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-191">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="7e452-191">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="7e452-192">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7e452-192">win:UnicodeString</span></span>|<span data-ttu-id="7e452-193">マネージド相互運用メソッドのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="7e452-193">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="7e452-194">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7e452-194">ClrInstanceID</span></span>|<span data-ttu-id="7e452-195">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7e452-195">win:UInt16</span></span>|<span data-ttu-id="7e452-196">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7e452-196">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e452-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e452-197">See also</span></span>

- [<span data-ttu-id="7e452-198">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7e452-198">CLR ETW Events</span></span>](clr-etw-events.md)
