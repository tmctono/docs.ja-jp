---
title: .NET Core でサポートされていない API
description: .NET Core で常に例外をスローする .NET Framework の API について説明します。
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901344"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="7b218-103">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="7b218-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="7b218-104">次の API は、指定されたプラットフォームの .NET Core で実行されると、常に <xref:System.PlatformNotSupportedException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="7b218-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="7b218-105">この記事では、影響を受ける API メンバーを名前空間別に整理しています。</span><span class="sxs-lookup"><span data-stu-id="7b218-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7b218-106">この記事は、作業中です。</span><span class="sxs-lookup"><span data-stu-id="7b218-106">This article is a work-in-progress.</span></span> <span data-ttu-id="7b218-107">.NET Core で例外をスローする API の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="7b218-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="7b218-108">この記事には、.NET Core でスローされるバイナリ シリアル化の明示的なインターフェイス実装は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7b218-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="7b218-109">詳細については、[.NET Core でのバイナリ シリアル化](../../standard/serialization/binary-serialization.md#net-core)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b218-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="7b218-110">システム</span><span class="sxs-lookup"><span data-stu-id="7b218-110">System</span></span>

| <span data-ttu-id="7b218-111">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-111">Member</span></span> | <span data-ttu-id="7b218-112">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-113">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="7b218-114">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="7b218-115">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="7b218-116">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-117">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="7b218-118">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7b218-119">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7b218-120">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-121">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7b218-122">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="7b218-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="7b218-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="7b218-124">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-124">Member</span></span> | <span data-ttu-id="7b218-125">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-126">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-127">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-128">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="7b218-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="7b218-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="7b218-130">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-130">Member</span></span> | <span data-ttu-id="7b218-131">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-132">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-133">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7b218-134">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="7b218-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="7b218-135">System.Configuration</span></span>

| <span data-ttu-id="7b218-136">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-136">Member</span></span> | <span data-ttu-id="7b218-137">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="7b218-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (すべてのメンバー)</span><span class="sxs-lookup"><span data-stu-id="7b218-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="7b218-139">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="7b218-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="7b218-140">System.Console</span></span>

| <span data-ttu-id="7b218-141">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-141">Member</span></span> | <span data-ttu-id="7b218-142">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="7b218-143">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-143">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-145">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-145">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-147">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-147">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-149">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-149">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7b218-151">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-152">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-153">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-154">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-154">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-155"><xref:System.Console.Title?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7b218-156">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-156">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-158">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-158">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-160">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-160">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-162">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-162">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-164">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="7b218-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="7b218-165">System.Data.Common</span></span>

| <span data-ttu-id="7b218-166">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-166">Member</span></span> | <span data-ttu-id="7b218-167">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="7b218-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (<xref:System.NotSupportedException> をスローする)</span><span class="sxs-lookup"><span data-stu-id="7b218-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="7b218-169">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="7b218-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7b218-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="7b218-171">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-171">Member</span></span> | <span data-ttu-id="7b218-172">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="7b218-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-174">Linux</span><span class="sxs-lookup"><span data-stu-id="7b218-174">Linux</span></span> |
| <span data-ttu-id="7b218-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-176">Linux</span><span class="sxs-lookup"><span data-stu-id="7b218-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="7b218-177">macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="7b218-178">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-179">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="7b218-180">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="7b218-181">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="7b218-182">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="7b218-183">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-183">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-185">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-185">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7b218-187">macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-187">macOS</span></span> |
| <span data-ttu-id="7b218-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-189">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="7b218-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="7b218-190">System.IO</span></span>

| <span data-ttu-id="7b218-191">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-191">Member</span></span> | <span data-ttu-id="7b218-192">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-193">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-194">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="7b218-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="7b218-195">System.IO.Pipes</span></span>

| <span data-ttu-id="7b218-196">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-196">Member</span></span> | <span data-ttu-id="7b218-197">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="7b218-198">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="7b218-199">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7b218-200">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7b218-201">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-201">Linux and macOS</span></span> |
| <span data-ttu-id="7b218-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-203">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="7b218-204">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="7b218-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="7b218-205">System.Media</span></span>

| <span data-ttu-id="7b218-206">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-206">Member</span></span> | <span data-ttu-id="7b218-207">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-208">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="7b218-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="7b218-209">System.Net</span></span>

| <span data-ttu-id="7b218-210">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-210">Member</span></span> | <span data-ttu-id="7b218-211">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7b218-212">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7b218-213">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-214">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-215">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-216">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-217">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-218">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-219">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-220">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-221">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-222">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="7b218-223">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-224">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-225">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-226">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-227">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-228">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="7b218-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="7b218-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="7b218-230">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-230">Member</span></span> | <span data-ttu-id="7b218-231">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="7b218-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="7b218-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="7b218-233">System.Net.Sockets</span></span>

| <span data-ttu-id="7b218-234">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-234">Member</span></span> | <span data-ttu-id="7b218-235">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="7b218-236">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="7b218-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="7b218-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="7b218-238">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-238">Member</span></span> | <span data-ttu-id="7b218-239">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="7b218-240">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="7b218-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="7b218-241">System.Reflection</span></span>

| <span data-ttu-id="7b218-242">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-242">Member</span></span> | <span data-ttu-id="7b218-243">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-244">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-245">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-246">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7b218-247">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-248">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-249">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="7b218-250">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="7b218-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="7b218-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="7b218-252">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-252">Member</span></span> | <span data-ttu-id="7b218-253">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="7b218-254">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="7b218-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="7b218-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="7b218-256">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-256">Member</span></span> | <span data-ttu-id="7b218-257">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7b218-258">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="7b218-259">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7b218-260">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7b218-261">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-262">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7b218-263">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7b218-264">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="7b218-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="7b218-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="7b218-266">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-266">Member</span></span> | <span data-ttu-id="7b218-267">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="7b218-268">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="7b218-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="7b218-269">System.Security</span></span>

| <span data-ttu-id="7b218-270">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-270">Member</span></span> | <span data-ttu-id="7b218-271">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="7b218-272">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7b218-273">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-274">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="7b218-275">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7b218-276">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="7b218-277">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="7b218-278">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="7b218-279">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7b218-280">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7b218-281">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="7b218-282">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7b218-283">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="7b218-284">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="7b218-285">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="7b218-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="7b218-286">System.Security.Claims</span></span>

| <span data-ttu-id="7b218-287">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-287">Member</span></span> | <span data-ttu-id="7b218-288">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="7b218-289">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-290">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="7b218-291">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-292">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-293">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="7b218-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="7b218-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="7b218-295">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-295">Member</span></span> | <span data-ttu-id="7b218-296">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-297">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-298">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="7b218-299">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="7b218-300">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="7b218-301">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7b218-302">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="7b218-303">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="7b218-304">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="7b218-305">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="7b218-306">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="7b218-307">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="7b218-308">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="7b218-309">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7b218-310">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7b218-311">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-312">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="7b218-313">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-314">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-315">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-316">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-317">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7b218-318">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-319">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-320">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-321">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="7b218-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-322">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-323">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7b218-324">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7b218-325">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="7b218-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="7b218-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="7b218-327">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-327">Member</span></span> | <span data-ttu-id="7b218-328">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="7b218-329">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7b218-330">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="7b218-331">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="7b218-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="7b218-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="7b218-333">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-333">Member</span></span> | <span data-ttu-id="7b218-334">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-335">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-336">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-337">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-337">All</span></span> |
| <span data-ttu-id="7b218-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="7b218-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7b218-339">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="7b218-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="7b218-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="7b218-341">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-341">Member</span></span> | <span data-ttu-id="7b218-342">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-343">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="7b218-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="7b218-344">System.Security.Policy</span></span>

| <span data-ttu-id="7b218-345">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-345">Member</span></span> | <span data-ttu-id="7b218-346">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-347">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="7b218-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="7b218-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="7b218-349">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-349">Member</span></span> | <span data-ttu-id="7b218-350">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-351">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="7b218-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="7b218-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="7b218-353">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-353">Member</span></span> | <span data-ttu-id="7b218-354">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-355">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="7b218-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="7b218-356">System.Threading</span></span>

| <span data-ttu-id="7b218-357">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-357">Member</span></span> | <span data-ttu-id="7b218-358">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-359">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7b218-360">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="7b218-361">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="7b218-362">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="7b218-363">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="7b218-364">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="7b218-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="7b218-365">System.Xml</span></span>

| <span data-ttu-id="7b218-366">メンバー</span><span class="sxs-lookup"><span data-stu-id="7b218-366">Member</span></span> | <span data-ttu-id="7b218-367">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="7b218-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7b218-368">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7b218-369">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7b218-370">すべて</span><span class="sxs-lookup"><span data-stu-id="7b218-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="7b218-371">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b218-371">See also</span></span>

- [<span data-ttu-id="7b218-372">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="7b218-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="7b218-373">.NET Core でのバイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="7b218-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="7b218-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="7b218-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
