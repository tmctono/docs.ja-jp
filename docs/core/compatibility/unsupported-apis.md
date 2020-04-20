---
title: .NET Core でサポートされていない API
titleSuffix: ''
description: .NET Core で常に例外をスローする .NET Framework の API について説明します。
ms.date: 12/23/2019
ms.openlocfilehash: bd3516d9480ef42b6ea89825ba64867a3ca104e3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242947"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="187e0-103">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="187e0-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="187e0-104">次の API は、すべてまたは一部のプラットフォームの .NET Core で <xref:System.PlatformNotSupportedException> を常にスローします。</span><span class="sxs-lookup"><span data-stu-id="187e0-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="187e0-105">この記事では、影響を受ける API メンバーを名前空間別に整理しています。</span><span class="sxs-lookup"><span data-stu-id="187e0-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="187e0-106">この記事は、作業中です。</span><span class="sxs-lookup"><span data-stu-id="187e0-106">This article is a work-in-progress.</span></span> <span data-ttu-id="187e0-107">.NET Core で例外をスローする API の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="187e0-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="187e0-108">この記事には、.NET Core でスローされるバイナリ シリアル化の明示的なインターフェイス実装は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="187e0-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="187e0-109">詳細については、[.NET Core でのバイナリ シリアル化](../../standard/serialization/binary-serialization.md#net-core)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="187e0-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="187e0-110">システム</span><span class="sxs-lookup"><span data-stu-id="187e0-110">System</span></span>

| <span data-ttu-id="187e0-111">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-111">Member</span></span> | <span data-ttu-id="187e0-112">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-113">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="187e0-114">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="187e0-115">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="187e0-116">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-117">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="187e0-118">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="187e0-119">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="187e0-120">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-121">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="187e0-122">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="187e0-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="187e0-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="187e0-124">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-124">Member</span></span> | <span data-ttu-id="187e0-125">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-126">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-127">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-128">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="187e0-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="187e0-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="187e0-130">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-130">Member</span></span> | <span data-ttu-id="187e0-131">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-132">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-133">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="187e0-134">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="187e0-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="187e0-135">System.Configuration</span></span>

| <span data-ttu-id="187e0-136">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-136">Member</span></span> | <span data-ttu-id="187e0-137">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="187e0-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (すべてのメンバー)</span><span class="sxs-lookup"><span data-stu-id="187e0-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="187e0-139">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="187e0-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="187e0-140">System.Console</span></span>

| <span data-ttu-id="187e0-141">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-141">Member</span></span> | <span data-ttu-id="187e0-142">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="187e0-143">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-143">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-145">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-145">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-147">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-147">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-149">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-149">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="187e0-151">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-152">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-153">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-154">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-154">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-155"><xref:System.Console.Title?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="187e0-156">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-156">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-158">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-158">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-160">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-160">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-162">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-162">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-164">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="187e0-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="187e0-165">System.Data.Common</span></span>

| <span data-ttu-id="187e0-166">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-166">Member</span></span> | <span data-ttu-id="187e0-167">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="187e0-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (<xref:System.NotSupportedException> をスローする)</span><span class="sxs-lookup"><span data-stu-id="187e0-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="187e0-169">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="187e0-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="187e0-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="187e0-171">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-171">Member</span></span> | <span data-ttu-id="187e0-172">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="187e0-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-174">Linux</span><span class="sxs-lookup"><span data-stu-id="187e0-174">Linux</span></span> |
| <span data-ttu-id="187e0-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-176">Linux</span><span class="sxs-lookup"><span data-stu-id="187e0-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="187e0-177">macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="187e0-178">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-179">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="187e0-180">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="187e0-181">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="187e0-182">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="187e0-183">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-183">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-185">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-185">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="187e0-187">macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-187">macOS</span></span> |
| <span data-ttu-id="187e0-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-189">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="187e0-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="187e0-190">System.IO</span></span>

| <span data-ttu-id="187e0-191">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-191">Member</span></span> | <span data-ttu-id="187e0-192">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-193">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-194">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="187e0-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="187e0-195">System.IO.Pipes</span></span>

| <span data-ttu-id="187e0-196">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-196">Member</span></span> | <span data-ttu-id="187e0-197">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="187e0-198">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="187e0-199">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="187e0-200">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="187e0-201">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-201">Linux and macOS</span></span> |
| <span data-ttu-id="187e0-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-203">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="187e0-204">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="187e0-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="187e0-205">System.Media</span></span>

| <span data-ttu-id="187e0-206">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-206">Member</span></span> | <span data-ttu-id="187e0-207">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-208">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="187e0-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="187e0-209">System.Net</span></span>

| <span data-ttu-id="187e0-210">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-210">Member</span></span> | <span data-ttu-id="187e0-211">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="187e0-212">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="187e0-213">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-214">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-215">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-216">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-217">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-218">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-219">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-220">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-221">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-222">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="187e0-223">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-224">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-225">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-226">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-227">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-228">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="187e0-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="187e0-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="187e0-230">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-230">Member</span></span> | <span data-ttu-id="187e0-231">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="187e0-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="187e0-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="187e0-233">System.Net.Sockets</span></span>

| <span data-ttu-id="187e0-234">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-234">Member</span></span> | <span data-ttu-id="187e0-235">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="187e0-236">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="187e0-237">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="187e0-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="187e0-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="187e0-239">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-239">Member</span></span> | <span data-ttu-id="187e0-240">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="187e0-241">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="187e0-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="187e0-242">System.Reflection</span></span>

| <span data-ttu-id="187e0-243">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-243">Member</span></span> | <span data-ttu-id="187e0-244">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-245">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-246">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-247">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="187e0-248">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="187e0-249">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-250">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="187e0-251">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="187e0-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="187e0-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="187e0-253">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-253">Member</span></span> | <span data-ttu-id="187e0-254">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="187e0-255">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="187e0-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="187e0-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="187e0-257">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-257">Member</span></span> | <span data-ttu-id="187e0-258">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="187e0-259">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="187e0-260">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="187e0-261">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="187e0-262">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-263">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="187e0-264">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="187e0-265">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="187e0-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="187e0-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="187e0-267">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-267">Member</span></span> | <span data-ttu-id="187e0-268">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="187e0-269">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="187e0-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="187e0-270">System.Security</span></span>

| <span data-ttu-id="187e0-271">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-271">Member</span></span> | <span data-ttu-id="187e0-272">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="187e0-273">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="187e0-274">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-275">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="187e0-276">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="187e0-277">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="187e0-278">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="187e0-279">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="187e0-280">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="187e0-281">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="187e0-282">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="187e0-283">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="187e0-284">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="187e0-285">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="187e0-286">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="187e0-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="187e0-287">System.Security.Claims</span></span>

| <span data-ttu-id="187e0-288">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-288">Member</span></span> | <span data-ttu-id="187e0-289">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="187e0-290">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-291">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="187e0-292">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-293">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-294">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="187e0-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="187e0-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="187e0-296">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-296">Member</span></span> | <span data-ttu-id="187e0-297">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-298">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="187e0-299">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="187e0-300">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="187e0-301">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="187e0-302">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="187e0-303">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="187e0-304">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="187e0-305">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="187e0-306">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="187e0-307">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="187e0-308">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="187e0-309">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="187e0-310">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="187e0-311">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="187e0-312">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="187e0-313">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-314">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-315">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-316">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-317">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="187e0-318">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-319">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-320">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-321">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="187e0-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-322">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-323">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="187e0-324">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="187e0-325">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="187e0-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="187e0-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="187e0-327">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-327">Member</span></span> | <span data-ttu-id="187e0-328">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="187e0-329">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="187e0-330">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="187e0-331">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="187e0-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="187e0-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="187e0-333">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-333">Member</span></span> | <span data-ttu-id="187e0-334">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-335">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-336">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-337">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-337">All</span></span> |
| <span data-ttu-id="187e0-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="187e0-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="187e0-339">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="187e0-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="187e0-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="187e0-341">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-341">Member</span></span> | <span data-ttu-id="187e0-342">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-343">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="187e0-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="187e0-344">System.Security.Policy</span></span>

| <span data-ttu-id="187e0-345">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-345">Member</span></span> | <span data-ttu-id="187e0-346">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-347">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="187e0-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="187e0-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="187e0-349">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-349">Member</span></span> | <span data-ttu-id="187e0-350">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="187e0-351">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="187e0-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="187e0-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="187e0-353">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-353">Member</span></span> | <span data-ttu-id="187e0-354">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-355">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="187e0-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="187e0-356">System.Threading</span></span>

| <span data-ttu-id="187e0-357">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-357">Member</span></span> | <span data-ttu-id="187e0-358">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-359">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="187e0-360">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="187e0-361">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="187e0-362">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="187e0-363">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="187e0-364">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="187e0-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="187e0-365">System.Xml</span></span>

| <span data-ttu-id="187e0-366">メンバー</span><span class="sxs-lookup"><span data-stu-id="187e0-366">Member</span></span> | <span data-ttu-id="187e0-367">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="187e0-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="187e0-368">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="187e0-369">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="187e0-370">すべて</span><span class="sxs-lookup"><span data-stu-id="187e0-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="187e0-371">参照</span><span class="sxs-lookup"><span data-stu-id="187e0-371">See also</span></span>

- [<span data-ttu-id="187e0-372">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="187e0-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="187e0-373">.NET Core でのバイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="187e0-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="187e0-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="187e0-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
