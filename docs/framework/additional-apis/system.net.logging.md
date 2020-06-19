---
title: Logging クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990542"
---
# <a name="logging-class"></a><span data-ttu-id="0770a-102">ログクラス</span><span class="sxs-lookup"><span data-stu-id="0770a-102">Logging class</span></span>

<span data-ttu-id="0770a-103">トレースログ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0770a-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="0770a-104">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0770a-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0770a-105">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0770a-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="0770a-106">関連付け方法</span><span class="sxs-lookup"><span data-stu-id="0770a-106">Associate method</span></span>

<span data-ttu-id="0770a-107">2つのオブジェクトが互いに関連付けられていることをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="0770a-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-108">Parameters</span></span>

- <span data-ttu-id="0770a-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-110">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-112">関連付けるオブジェクト `objB` 。</span><span class="sxs-lookup"><span data-stu-id="0770a-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="0770a-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-114">関連付けるオブジェクト `objA` 。</span><span class="sxs-lookup"><span data-stu-id="0770a-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="0770a-115">Enter (TraceSource、object、string、string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="0770a-116">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="0770a-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-117">Parameters</span></span>

- <span data-ttu-id="0770a-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-119">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-121">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-121">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-123">入力されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-123">The method that is being entered.</span></span>

- <span data-ttu-id="0770a-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="0770a-125">メソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="0770a-126">Enter (TraceSource、object、string、object) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="0770a-127">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="0770a-128">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-128">Parameters</span></span>

- <span data-ttu-id="0770a-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-130">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-132">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-132">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-134">入力されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-134">The method that is being entered.</span></span>

- <span data-ttu-id="0770a-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-136">メソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="0770a-137">Enter (TraceSource、string、string、string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="0770a-138">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="0770a-139">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-139">Parameters</span></span>

- <span data-ttu-id="0770a-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-141">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0770a-143">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-143">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-145">入力されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-145">The method that is being entered.</span></span>

- <span data-ttu-id="0770a-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="0770a-147">メソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="0770a-148">Enter (TraceSource、string、string、object) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="0770a-149">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="0770a-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-150">Parameters</span></span>

- <span data-ttu-id="0770a-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-152">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0770a-154">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-154">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-156">入力されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-156">The method that is being entered.</span></span>

- <span data-ttu-id="0770a-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-158">メソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="0770a-159">Enter (TraceSource, string, string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="0770a-160">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="0770a-161">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-161">Parameters</span></span>

- <span data-ttu-id="0770a-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-163">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-165">入力されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-165">The method that is being entered.</span></span>

- <span data-ttu-id="0770a-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="0770a-167">メソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="0770a-168">Enter (TraceSource, string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="0770a-169">メソッドへの入り口をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="0770a-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="0770a-170">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-170">Parameters</span></span>

- <span data-ttu-id="0770a-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-172">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="0770a-174">トレースソースにログを記録するための開始メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0770a-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="0770a-175">Exception メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-175">Exception method</span></span>

<span data-ttu-id="0770a-176">例外をログに記録し、インデントを復元します。</span><span class="sxs-lookup"><span data-stu-id="0770a-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="0770a-177">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-177">Parameters</span></span>

- <span data-ttu-id="0770a-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-179">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-181">例外をスローしたメソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="0770a-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-183">例外をスローしたメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-183">The method that threw the exception.</span></span>

- <span data-ttu-id="0770a-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="0770a-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="0770a-185">スローされた例外。</span><span class="sxs-lookup"><span data-stu-id="0770a-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="0770a-186">Exit (TraceSource、object、string、object) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="0770a-187">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="0770a-188">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-188">Parameters</span></span>

- <span data-ttu-id="0770a-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-190">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-192">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-192">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-194">終了されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-194">The method that is being exited.</span></span>

- <span data-ttu-id="0770a-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-196">メソッドによって返される値。</span><span class="sxs-lookup"><span data-stu-id="0770a-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="0770a-197">Exit (TraceSource、string、string、object) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="0770a-198">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="0770a-199">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-199">Parameters</span></span>

- <span data-ttu-id="0770a-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-201">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0770a-203">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-203">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-205">終了されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-205">The method that is being exited.</span></span>

- <span data-ttu-id="0770a-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-207">メソッドによって返される値。</span><span class="sxs-lookup"><span data-stu-id="0770a-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="0770a-208">Exit (TraceSource、object、string、string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="0770a-209">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="0770a-210">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-210">Parameters</span></span>

- <span data-ttu-id="0770a-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-212">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0770a-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0770a-214">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-214">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-216">終了されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-216">The method that is being exited.</span></span>

- <span data-ttu-id="0770a-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="0770a-218">メソッドによって返される値。</span><span class="sxs-lookup"><span data-stu-id="0770a-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="0770a-219">Exit (TraceSource、string、string、string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="0770a-220">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="0770a-221">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-221">Parameters</span></span>

- <span data-ttu-id="0770a-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-223">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0770a-225">メソッドが呼び出されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0770a-225">The object that the method was called on.</span></span>

- <span data-ttu-id="0770a-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-227">終了されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-227">The method that is being exited.</span></span>

- <span data-ttu-id="0770a-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="0770a-229">メソッドによって返される値。</span><span class="sxs-lookup"><span data-stu-id="0770a-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="0770a-230">Exit (TraceSource, string, string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="0770a-231">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="0770a-232">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-232">Parameters</span></span>

- <span data-ttu-id="0770a-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-234">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="0770a-236">終了されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="0770a-236">The method that is being exited.</span></span>

- <span data-ttu-id="0770a-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="0770a-238">終了されるメソッドに渡されたパラメーター。</span><span class="sxs-lookup"><span data-stu-id="0770a-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="0770a-239">Exit (TraceSource, string) メソッド</span><span class="sxs-lookup"><span data-stu-id="0770a-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="0770a-240">ログは関数から終了します。</span><span class="sxs-lookup"><span data-stu-id="0770a-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="0770a-241">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0770a-241">Parameters</span></span>

- <span data-ttu-id="0770a-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0770a-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0770a-243">イベントのログを記録するトレースソース。</span><span class="sxs-lookup"><span data-stu-id="0770a-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="0770a-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0770a-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="0770a-245">トレースソースに記録する終了メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0770a-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="0770a-246">Http プロパティ</span><span class="sxs-lookup"><span data-stu-id="0770a-246">Http property</span></span>

<span data-ttu-id="0770a-247">"System .Net. Http" のトレースソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="0770a-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="0770a-248">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="0770a-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="0770a-249">"System .Net. Http" のトレースソース `null` 。ログ記録が有効になっていない場合は。</span><span class="sxs-lookup"><span data-stu-id="0770a-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="0770a-250">On プロパティ</span><span class="sxs-lookup"><span data-stu-id="0770a-250">On property</span></span>

<span data-ttu-id="0770a-251">ログが有効になっているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0770a-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="0770a-252">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="0770a-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="0770a-253">ログが可能な場合は `true`、それ以外の場合は `false` です。</span><span class="sxs-lookup"><span data-stu-id="0770a-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0770a-254">必要条件</span><span class="sxs-lookup"><span data-stu-id="0770a-254">Requirements</span></span>

<span data-ttu-id="0770a-255">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0770a-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0770a-256">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="0770a-256">**Assembly:** System (in System.dll)</span></span>
