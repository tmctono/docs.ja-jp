---
title: 基本クラス ライブラリの破壊的変更
description: Core .NET ライブラリにおける破壊的変更の一覧を示します。
ms.date: 07/27/2020
ms.openlocfilehash: c73909514bc738387a21f5ea68defe49c6a2c839
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598184"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="1f7ee-103">Core .NET ライブラリの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="1f7ee-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="1f7ee-104">Core .NET ライブラリでは、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f7ee-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="1f7ee-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f7ee-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="1f7ee-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="1f7ee-106">Breaking change</span></span> | <span data-ttu-id="1f7ee-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="1f7ee-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="1f7ee-108">Thread.Abort は古い形式</span><span class="sxs-lookup"><span data-stu-id="1f7ee-108">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="1f7ee-109">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-109">5.0</span></span> |
| [<span data-ttu-id="1f7ee-110">ConsoleLoggerOptions の古いプロパティ</span><span class="sxs-lookup"><span data-stu-id="1f7ee-110">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="1f7ee-111">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-111">5.0</span></span> |
| [<span data-ttu-id="1f7ee-112">ハードウェアに組み込みの IsSupported チェックは、入れ子にされた型によって異なる場合があります</span><span class="sxs-lookup"><span data-stu-id="1f7ee-112">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="1f7ee-113">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-113">5.0</span></span> |
| [<span data-ttu-id="1f7ee-114">参照アセンブリのパラメーター名の変更</span><span class="sxs-lookup"><span data-stu-id="1f7ee-114">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="1f7ee-115">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-115">5.0</span></span> |
| [<span data-ttu-id="1f7ee-116">Unix 上で ASCII 以外の文字を含む URI パスが正しく解析される</span><span class="sxs-lookup"><span data-stu-id="1f7ee-116">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="1f7ee-117">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-117">5.0</span></span> |
| [<span data-ttu-id="1f7ee-118">Unix での UNC パスの URI 認識</span><span class="sxs-lookup"><span data-stu-id="1f7ee-118">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="1f7ee-119">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-119">5.0</span></span> |
| [<span data-ttu-id="1f7ee-120">Environment.OSVersion で正しいオペレーティング システム バージョンが返される</span><span class="sxs-lookup"><span data-stu-id="1f7ee-120">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="1f7ee-121">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-121">5.0</span></span> |
| [<span data-ttu-id="1f7ee-122">LINQ OrderBy.First{OrDefault} の複雑さが増大</span><span class="sxs-lookup"><span data-stu-id="1f7ee-122">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="1f7ee-123">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-123">5.0</span></span> |
| [<span data-ttu-id="1f7ee-124">IntPtr と UIntPtr の IFormattable 実装</span><span class="sxs-lookup"><span data-stu-id="1f7ee-124">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="1f7ee-125">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-125">5.0</span></span> |
| [<span data-ttu-id="1f7ee-126">PrincipalPermissionAttribute は現在使用されていないエラーです</span><span class="sxs-lookup"><span data-stu-id="1f7ee-126">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="1f7ee-127">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-127">5.0</span></span> |
| [<span data-ttu-id="1f7ee-128">BinaryFormatter シリアル化メソッドが古い形式になり、ASP.NET アプリでは使用不可に</span><span class="sxs-lookup"><span data-stu-id="1f7ee-128">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="1f7ee-129">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-129">5.0</span></span> |
| [<span data-ttu-id="1f7ee-130">UTF-7 コード パスが古い形式に</span><span class="sxs-lookup"><span data-stu-id="1f7ee-130">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="1f7ee-131">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-131">5.0</span></span> |
| [<span data-ttu-id="1f7ee-132">Vector\<T> で、サポートされない型に対して常に NotSupportedException がスローされる</span><span class="sxs-lookup"><span data-stu-id="1f7ee-132">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="1f7ee-133">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-133">5.0</span></span> |
| [<span data-ttu-id="1f7ee-134">既定の ActivityIdFormat は W3C</span><span class="sxs-lookup"><span data-stu-id="1f7ee-134">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="1f7ee-135">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-135">5.0</span></span> |
| [<span data-ttu-id="1f7ee-136">Vector2.Lerp と Vector4.Lerp の動作の変更</span><span class="sxs-lookup"><span data-stu-id="1f7ee-136">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="1f7ee-137">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-137">5.0</span></span> |
| [<span data-ttu-id="1f7ee-138">SSE および SSE2 の CompareGreaterThan メソッドで NaN 入力が正しく処理されるようになった</span><span class="sxs-lookup"><span data-stu-id="1f7ee-138">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="1f7ee-139">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-139">5.0</span></span> |
| [<span data-ttu-id="1f7ee-140">インスタンスが既に存在する場合、CounterSet.CreateCounterSetInstance は InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="1f7ee-140">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="1f7ee-141">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-141">5.0</span></span> |
| [<span data-ttu-id="1f7ee-142">Microsoft.DotNet.PlatformAbstractions パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="1f7ee-142">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="1f7ee-143">5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-143">5.0</span></span> |
| [<span data-ttu-id="1f7ee-144">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="1f7ee-144">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="1f7ee-145">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-145">3.0</span></span> |
| [<span data-ttu-id="1f7ee-146">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="1f7ee-146">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="1f7ee-147">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-147">3.0</span></span> |
| [<span data-ttu-id="1f7ee-148">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="1f7ee-148">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="1f7ee-149">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-149">3.0</span></span> |
| [<span data-ttu-id="1f7ee-150">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="1f7ee-150">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="1f7ee-151">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-151">3.0</span></span> |
| [<span data-ttu-id="1f7ee-152">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="1f7ee-152">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="1f7ee-153">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-153">3.0</span></span> |
| [<span data-ttu-id="1f7ee-154">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="1f7ee-154">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="1f7ee-155">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-155">3.0</span></span> |
| [<span data-ttu-id="1f7ee-156">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="1f7ee-156">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="1f7ee-157">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-157">3.0</span></span> |
| [<span data-ttu-id="1f7ee-158">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="1f7ee-158">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="1f7ee-159">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-159">3.0</span></span> |
| [<span data-ttu-id="1f7ee-160">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="1f7ee-160">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="1f7ee-161">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-161">3.0</span></span> |
| [<span data-ttu-id="1f7ee-162">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="1f7ee-162">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="1f7ee-163">2.1</span><span class="sxs-lookup"><span data-stu-id="1f7ee-163">2.1</span></span> |
| [<span data-ttu-id="1f7ee-164">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="1f7ee-164">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="1f7ee-165">2.1</span><span class="sxs-lookup"><span data-stu-id="1f7ee-165">2.1</span></span> |
| [<span data-ttu-id="1f7ee-166">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="1f7ee-166">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="1f7ee-167">2.1</span><span class="sxs-lookup"><span data-stu-id="1f7ee-167">2.1</span></span> |
| [<span data-ttu-id="1f7ee-168">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="1f7ee-168">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="1f7ee-169">1.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-169">1.0</span></span> |
| [<span data-ttu-id="1f7ee-170">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="1f7ee-170">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="1f7ee-171">1.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-171">1.0</span></span> |
| [<span data-ttu-id="1f7ee-172">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="1f7ee-172">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="1f7ee-173">1.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-173">1.0</span></span> |
| [<span data-ttu-id="1f7ee-174">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="1f7ee-174">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="1f7ee-175">1.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-175">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="1f7ee-176">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-176">.NET 5.0</span></span>

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

***

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="1f7ee-177">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-177">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="1f7ee-178">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1f7ee-178">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="1f7ee-179">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="1f7ee-179">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
