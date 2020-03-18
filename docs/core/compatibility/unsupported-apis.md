---
title: .NET Core でサポートされていない API
titleSuffix: ''
description: .NET Core で常に例外をスローする .NET Framework の API について説明します。
ms.date: 12/23/2019
ms.openlocfilehash: c4b94321d30cacd90d5c2ee23c258681683a6faa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092968"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="9bc0c-103">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="9bc0c-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="9bc0c-104">次の API は、すべてまたは一部のプラットフォームの .NET Core で <xref:System.PlatformNotSupportedException> を常にスローします。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="9bc0c-105">この記事では、影響を受ける API メンバーを名前空間別に整理しています。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9bc0c-106">この記事は、作業中です。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-106">This article is a work-in-progress.</span></span> <span data-ttu-id="9bc0c-107">.NET Core で例外をスローする API の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="9bc0c-108">この記事には、.NET Core でスローされるバイナリ シリアル化の明示的なインターフェイス実装は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="9bc0c-109">詳細については、[.NET Core でのバイナリ シリアル化](../../standard/serialization/binary-serialization.md#net-core)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc0c-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="9bc0c-110">システム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-110">System</span></span>

| <span data-ttu-id="9bc0c-111">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-111">Member</span></span> | <span data-ttu-id="9bc0c-112">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-113">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-114">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-115">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-116">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-117">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-118">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-119">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-120">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-121">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-122">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="9bc0c-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="9bc0c-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="9bc0c-124">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-124">Member</span></span> | <span data-ttu-id="9bc0c-125">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-126">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-127">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-128">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="9bc0c-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="9bc0c-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="9bc0c-130">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-130">Member</span></span> | <span data-ttu-id="9bc0c-131">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-132">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-133">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-134">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="9bc0c-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="9bc0c-135">System.Configuration</span></span>

| <span data-ttu-id="9bc0c-136">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-136">Member</span></span> | <span data-ttu-id="9bc0c-137">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bc0c-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (すべてのメンバー)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="9bc0c-139">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="9bc0c-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="9bc0c-140">System.Console</span></span>

| <span data-ttu-id="9bc0c-141">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-141">Member</span></span> | <span data-ttu-id="9bc0c-142">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-143">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-143">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-145">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-145">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-147">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-147">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-149">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-149">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bc0c-151">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-152">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-153">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-154">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-154">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-155"><xref:System.Console.Title?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bc0c-156">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-156">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-158">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-158">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-160">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-160">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-162">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-162">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-164">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="9bc0c-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="9bc0c-165">System.Data.Common</span></span>

| <span data-ttu-id="9bc0c-166">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-166">Member</span></span> | <span data-ttu-id="9bc0c-167">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bc0c-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (<xref:System.NotSupportedException> をスローする)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="9bc0c-169">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="9bc0c-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="9bc0c-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="9bc0c-171">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-171">Member</span></span> | <span data-ttu-id="9bc0c-172">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bc0c-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-174">Linux</span><span class="sxs-lookup"><span data-stu-id="9bc0c-174">Linux</span></span> |
| <span data-ttu-id="9bc0c-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-176">Linux</span><span class="sxs-lookup"><span data-stu-id="9bc0c-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-177">macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-178">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-179">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-180">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-181">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-182">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-183">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-183">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-185">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-185">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bc0c-187">macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-187">macOS</span></span> |
| <span data-ttu-id="9bc0c-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-189">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="9bc0c-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="9bc0c-190">System.IO</span></span>

| <span data-ttu-id="9bc0c-191">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-191">Member</span></span> | <span data-ttu-id="9bc0c-192">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-193">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-194">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="9bc0c-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="9bc0c-195">System.IO.Pipes</span></span>

| <span data-ttu-id="9bc0c-196">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-196">Member</span></span> | <span data-ttu-id="9bc0c-197">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-198">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-199">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-200">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-201">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-201">Linux and macOS</span></span> |
| <span data-ttu-id="9bc0c-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-203">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-204">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="9bc0c-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="9bc0c-205">System.Media</span></span>

| <span data-ttu-id="9bc0c-206">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-206">Member</span></span> | <span data-ttu-id="9bc0c-207">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-208">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="9bc0c-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="9bc0c-209">System.Net</span></span>

| <span data-ttu-id="9bc0c-210">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-210">Member</span></span> | <span data-ttu-id="9bc0c-211">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-212">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-213">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-214">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-215">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-216">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-217">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-218">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-219">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-220">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-221">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-222">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-223">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-224">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-225">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-226">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-227">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-228">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="9bc0c-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="9bc0c-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="9bc0c-230">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-230">Member</span></span> | <span data-ttu-id="9bc0c-231">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="9bc0c-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="9bc0c-233">System.Net.Sockets</span></span>

| <span data-ttu-id="9bc0c-234">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-234">Member</span></span> | <span data-ttu-id="9bc0c-235">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-236">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-237">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="9bc0c-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="9bc0c-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="9bc0c-239">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-239">Member</span></span> | <span data-ttu-id="9bc0c-240">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-241">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="9bc0c-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="9bc0c-242">System.Reflection</span></span>

| <span data-ttu-id="9bc0c-243">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-243">Member</span></span> | <span data-ttu-id="9bc0c-244">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-245">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-246">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-247">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-248">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-249">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-250">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-251">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="9bc0c-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="9bc0c-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="9bc0c-253">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-253">Member</span></span> | <span data-ttu-id="9bc0c-254">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-255">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="9bc0c-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="9bc0c-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="9bc0c-257">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-257">Member</span></span> | <span data-ttu-id="9bc0c-258">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-259">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-260">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-261">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-262">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-263">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-264">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-265">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="9bc0c-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="9bc0c-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="9bc0c-267">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-267">Member</span></span> | <span data-ttu-id="9bc0c-268">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-269">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="9bc0c-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="9bc0c-270">System.Security</span></span>

| <span data-ttu-id="9bc0c-271">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-271">Member</span></span> | <span data-ttu-id="9bc0c-272">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-273">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-274">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-275">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-276">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-277">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-278">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-279">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-280">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-281">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-282">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-283">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-284">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-285">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-286">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="9bc0c-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="9bc0c-287">System.Security.Claims</span></span>

| <span data-ttu-id="9bc0c-288">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-288">Member</span></span> | <span data-ttu-id="9bc0c-289">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-290">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-291">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-292">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-293">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-294">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="9bc0c-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="9bc0c-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="9bc0c-296">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-296">Member</span></span> | <span data-ttu-id="9bc0c-297">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-298">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-299">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-300">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-301">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-302">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-303">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-304">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-305">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-306">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-307">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-308">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-309">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-310">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-311">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-312">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-313">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-314">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-315">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-316">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-317">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-318">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-319">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-320">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-321">Linux と macOS</span><span class="sxs-lookup"><span data-stu-id="9bc0c-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-322">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-323">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-324">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-325">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="9bc0c-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="9bc0c-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="9bc0c-327">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-327">Member</span></span> | <span data-ttu-id="9bc0c-328">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-329">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-330">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-331">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="9bc0c-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="9bc0c-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="9bc0c-333">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-333">Member</span></span> | <span data-ttu-id="9bc0c-334">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-335">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-336">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-337">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-337">All</span></span> |
| <span data-ttu-id="9bc0c-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set のみ)</span><span class="sxs-lookup"><span data-stu-id="9bc0c-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bc0c-339">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="9bc0c-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="9bc0c-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="9bc0c-341">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-341">Member</span></span> | <span data-ttu-id="9bc0c-342">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-343">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="9bc0c-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="9bc0c-344">System.Security.Policy</span></span>

| <span data-ttu-id="9bc0c-345">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-345">Member</span></span> | <span data-ttu-id="9bc0c-346">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-347">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="9bc0c-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="9bc0c-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="9bc0c-349">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-349">Member</span></span> | <span data-ttu-id="9bc0c-350">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-351">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="9bc0c-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="9bc0c-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="9bc0c-353">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-353">Member</span></span> | <span data-ttu-id="9bc0c-354">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-355">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="9bc0c-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="9bc0c-356">System.Threading</span></span>

| <span data-ttu-id="9bc0c-357">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-357">Member</span></span> | <span data-ttu-id="9bc0c-358">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-359">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-360">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-361">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-362">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-363">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-364">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="9bc0c-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="9bc0c-365">System.Xml</span></span>

| <span data-ttu-id="9bc0c-366">メンバー</span><span class="sxs-lookup"><span data-stu-id="9bc0c-366">Member</span></span> | <span data-ttu-id="9bc0c-367">スローするプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9bc0c-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-368">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-369">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bc0c-370">すべて</span><span class="sxs-lookup"><span data-stu-id="9bc0c-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="9bc0c-371">参照</span><span class="sxs-lookup"><span data-stu-id="9bc0c-371">See also</span></span>

- [<span data-ttu-id="9bc0c-372">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="9bc0c-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="9bc0c-373">.NET Core でのバイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="9bc0c-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="9bc0c-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="9bc0c-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
