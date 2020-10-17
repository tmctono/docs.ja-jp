---
title: 基本クラス ライブラリの破壊的変更
description: Core .NET ライブラリにおける破壊的変更の一覧を示します。
ms.date: 07/27/2020
ms.openlocfilehash: d4deef295479b1f32bd72a69369a11c7375835f4
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955560"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="cfa5d-103">Core .NET ライブラリの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="cfa5d-104">Core .NET ライブラリでは、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="cfa5d-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="cfa5d-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfa5d-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cfa5d-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="cfa5d-106">Breaking change</span></span> | <span data-ttu-id="cfa5d-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cfa5d-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cfa5d-108">単一ファイル発行形式のアセンブリ関連 API 動作の変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-108">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="cfa5d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-109">5.0</span></span> |
| [<span data-ttu-id="cfa5d-110">Activity.Tags 内のタグの順序が逆になっている</span><span class="sxs-lookup"><span data-stu-id="cfa5d-110">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="cfa5d-111">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-111">5.0</span></span> |
| [<span data-ttu-id="cfa5d-112">RC1 でパラメーター名が変更されている</span><span class="sxs-lookup"><span data-stu-id="cfa5d-112">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="cfa5d-113">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-113">5.0</span></span> |
| [<span data-ttu-id="cfa5d-114">OSPlatform 属性の名前変更または削除</span><span class="sxs-lookup"><span data-stu-id="cfa5d-114">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="cfa5d-115">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-115">5.0</span></span> |
| [<span data-ttu-id="cfa5d-116">Thread.Abort は古い形式</span><span class="sxs-lookup"><span data-stu-id="cfa5d-116">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="cfa5d-117">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-117">5.0</span></span> |
| [<span data-ttu-id="cfa5d-118">ConsoleLoggerOptions の古いプロパティ</span><span class="sxs-lookup"><span data-stu-id="cfa5d-118">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="cfa5d-119">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-119">5.0</span></span> |
| [<span data-ttu-id="cfa5d-120">ハードウェアに組み込みの IsSupported チェックは、入れ子にされた型によって異なる場合があります</span><span class="sxs-lookup"><span data-stu-id="cfa5d-120">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="cfa5d-121">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-121">5.0</span></span> |
| [<span data-ttu-id="cfa5d-122">参照アセンブリのパラメーター名の変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-122">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="cfa5d-123">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-123">5.0</span></span> |
| [<span data-ttu-id="cfa5d-124">Unix 上で ASCII 以外の文字を含む URI パスが正しく解析される</span><span class="sxs-lookup"><span data-stu-id="cfa5d-124">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="cfa5d-125">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-125">5.0</span></span> |
| [<span data-ttu-id="cfa5d-126">Unix での UNC パスの URI 認識</span><span class="sxs-lookup"><span data-stu-id="cfa5d-126">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="cfa5d-127">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-127">5.0</span></span> |
| [<span data-ttu-id="cfa5d-128">Environment.OSVersion で正しいオペレーティング システム バージョンが返される</span><span class="sxs-lookup"><span data-stu-id="cfa5d-128">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="cfa5d-129">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-129">5.0</span></span> |
| [<span data-ttu-id="cfa5d-130">LINQ OrderBy.First{OrDefault} の複雑さが増大</span><span class="sxs-lookup"><span data-stu-id="cfa5d-130">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="cfa5d-131">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-131">5.0</span></span> |
| [<span data-ttu-id="cfa5d-132">IntPtr と UIntPtr の IFormattable 実装</span><span class="sxs-lookup"><span data-stu-id="cfa5d-132">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="cfa5d-133">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-133">5.0</span></span> |
| [<span data-ttu-id="cfa5d-134">PrincipalPermissionAttribute は現在使用されていないエラーです</span><span class="sxs-lookup"><span data-stu-id="cfa5d-134">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="cfa5d-135">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-135">5.0</span></span> |
| [<span data-ttu-id="cfa5d-136">BinaryFormatter シリアル化メソッドが古い形式になり、ASP.NET アプリでは使用不可に</span><span class="sxs-lookup"><span data-stu-id="cfa5d-136">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="cfa5d-137">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-137">5.0</span></span> |
| [<span data-ttu-id="cfa5d-138">UTF-7 コード パスが古い形式に</span><span class="sxs-lookup"><span data-stu-id="cfa5d-138">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="cfa5d-139">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-139">5.0</span></span> |
| [<span data-ttu-id="cfa5d-140">Vector\<T> で、サポートされない型に対して常に NotSupportedException がスローされる</span><span class="sxs-lookup"><span data-stu-id="cfa5d-140">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="cfa5d-141">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-141">5.0</span></span> |
| [<span data-ttu-id="cfa5d-142">既定の ActivityIdFormat は W3C</span><span class="sxs-lookup"><span data-stu-id="cfa5d-142">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="cfa5d-143">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-143">5.0</span></span> |
| [<span data-ttu-id="cfa5d-144">Vector2.Lerp と Vector4.Lerp の動作の変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-144">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="cfa5d-145">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-145">5.0</span></span> |
| [<span data-ttu-id="cfa5d-146">SSE および SSE2 の CompareGreaterThan メソッドで NaN 入力が正しく処理されるようになった</span><span class="sxs-lookup"><span data-stu-id="cfa5d-146">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="cfa5d-147">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-147">5.0</span></span> |
| [<span data-ttu-id="cfa5d-148">インスタンスが既に存在する場合、CounterSet.CreateCounterSetInstance は InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="cfa5d-148">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="cfa5d-149">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-149">5.0</span></span> |
| [<span data-ttu-id="cfa5d-150">Microsoft.DotNet.PlatformAbstractions パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="cfa5d-150">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="cfa5d-151">5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-151">5.0</span></span> |
| [<span data-ttu-id="cfa5d-152">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="cfa5d-152">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="cfa5d-153">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-153">3.0</span></span> |
| [<span data-ttu-id="cfa5d-154">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="cfa5d-154">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="cfa5d-155">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-155">3.0</span></span> |
| [<span data-ttu-id="cfa5d-156">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-156">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="cfa5d-157">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-157">3.0</span></span> |
| [<span data-ttu-id="cfa5d-158">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="cfa5d-158">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="cfa5d-159">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-159">3.0</span></span> |
| [<span data-ttu-id="cfa5d-160">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="cfa5d-160">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="cfa5d-161">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-161">3.0</span></span> |
| [<span data-ttu-id="cfa5d-162">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="cfa5d-162">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="cfa5d-163">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-163">3.0</span></span> |
| [<span data-ttu-id="cfa5d-164">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="cfa5d-164">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="cfa5d-165">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-165">3.0</span></span> |
| [<span data-ttu-id="cfa5d-166">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="cfa5d-166">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="cfa5d-167">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-167">3.0</span></span> |
| [<span data-ttu-id="cfa5d-168">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="cfa5d-168">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="cfa5d-169">3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-169">3.0</span></span> |
| [<span data-ttu-id="cfa5d-170">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="cfa5d-170">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="cfa5d-171">2.1</span><span class="sxs-lookup"><span data-stu-id="cfa5d-171">2.1</span></span> |
| [<span data-ttu-id="cfa5d-172">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="cfa5d-172">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="cfa5d-173">2.1</span><span class="sxs-lookup"><span data-stu-id="cfa5d-173">2.1</span></span> |
| [<span data-ttu-id="cfa5d-174">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="cfa5d-174">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="cfa5d-175">2.1</span><span class="sxs-lookup"><span data-stu-id="cfa5d-175">2.1</span></span> |
| [<span data-ttu-id="cfa5d-176">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="cfa5d-176">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="cfa5d-177">1.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-177">1.0</span></span> |
| [<span data-ttu-id="cfa5d-178">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="cfa5d-178">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="cfa5d-179">1.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-179">1.0</span></span> |
| [<span data-ttu-id="cfa5d-180">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="cfa5d-180">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="cfa5d-181">1.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-181">1.0</span></span> |
| [<span data-ttu-id="cfa5d-182">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="cfa5d-182">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="cfa5d-183">1.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-183">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cfa5d-184">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-184">.NET 5.0</span></span>

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

***

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

***

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

***

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="cfa5d-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-185">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="cfa5d-186">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cfa5d-186">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="cfa5d-187">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="cfa5d-187">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
