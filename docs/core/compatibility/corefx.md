---
title: 基本クラス ライブラリの破壊的変更
description: Core .NET ライブラリにおける破壊的変更の一覧を示します。
ms.date: 07/27/2020
ms.openlocfilehash: 558aa1d76831cd15e2028c17d2b0b2e82f64ef9a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517329"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="17a8d-103">Core .NET ライブラリの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="17a8d-104">Core .NET ライブラリでは、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="17a8d-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="17a8d-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="17a8d-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="17a8d-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="17a8d-106">Breaking change</span></span> | <span data-ttu-id="17a8d-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="17a8d-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="17a8d-108">BinaryFormatter シリアル化メソッドが古い形式になり、ASP.NET アプリでは使用不可に</span><span class="sxs-lookup"><span data-stu-id="17a8d-108">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="17a8d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-109">5.0</span></span> |
| [<span data-ttu-id="17a8d-110">UTF-7 コード パスが古い形式に</span><span class="sxs-lookup"><span data-stu-id="17a8d-110">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="17a8d-111">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-111">5.0</span></span> |
| [<span data-ttu-id="17a8d-112">Vector\<T> で、サポートされない型に対して常に NotSupportedException がスローされる</span><span class="sxs-lookup"><span data-stu-id="17a8d-112">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="17a8d-113">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-113">5.0</span></span> |
| [<span data-ttu-id="17a8d-114">既定の ActivityIdFormat は W3C</span><span class="sxs-lookup"><span data-stu-id="17a8d-114">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="17a8d-115">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-115">5.0</span></span> |
| [<span data-ttu-id="17a8d-116">Vector2.Lerp と Vector4.Lerp の動作の変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-116">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="17a8d-117">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-117">5.0</span></span> |
| [<span data-ttu-id="17a8d-118">SSE および SSE2 の CompareGreaterThan メソッドで NaN 入力が正しく処理されるようになった</span><span class="sxs-lookup"><span data-stu-id="17a8d-118">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="17a8d-119">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-119">5.0</span></span> |
| [<span data-ttu-id="17a8d-120">インスタンスが既に存在する場合、CounterSet.CreateCounterSetInstance は InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="17a8d-120">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="17a8d-121">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-121">5.0</span></span> |
| [<span data-ttu-id="17a8d-122">Microsoft.DotNet.PlatformAbstractions パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="17a8d-122">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="17a8d-123">5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-123">5.0</span></span> |
| [<span data-ttu-id="17a8d-124">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="17a8d-124">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="17a8d-125">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-125">3.0</span></span> |
| [<span data-ttu-id="17a8d-126">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="17a8d-126">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="17a8d-127">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-127">3.0</span></span> |
| [<span data-ttu-id="17a8d-128">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-128">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="17a8d-129">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-129">3.0</span></span> |
| [<span data-ttu-id="17a8d-130">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="17a8d-130">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="17a8d-131">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-131">3.0</span></span> |
| [<span data-ttu-id="17a8d-132">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="17a8d-132">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="17a8d-133">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-133">3.0</span></span> |
| [<span data-ttu-id="17a8d-134">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="17a8d-134">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="17a8d-135">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-135">3.0</span></span> |
| [<span data-ttu-id="17a8d-136">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="17a8d-136">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="17a8d-137">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-137">3.0</span></span> |
| [<span data-ttu-id="17a8d-138">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="17a8d-138">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="17a8d-139">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-139">3.0</span></span> |
| [<span data-ttu-id="17a8d-140">Utf8JsonWriter での (string)null のセマンティクスの変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-140">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="17a8d-141">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-141">3.0</span></span> |
| [<span data-ttu-id="17a8d-142">JsonEncodedText.Encode メソッドに JavaScriptEncoder 引数を追加</span><span class="sxs-lookup"><span data-stu-id="17a8d-142">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="17a8d-143">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-143">3.0</span></span> |
| [<span data-ttu-id="17a8d-144">JsonFactoryConverter.CreateConverter 署名の変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-144">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="17a8d-145">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-145">3.0</span></span> |
| [<span data-ttu-id="17a8d-146">JsonElement API の変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-146">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="17a8d-147">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-147">3.0</span></span> |
| [<span data-ttu-id="17a8d-148">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="17a8d-148">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="17a8d-149">3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-149">3.0</span></span> |
| [<span data-ttu-id="17a8d-150">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="17a8d-150">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="17a8d-151">2.1</span><span class="sxs-lookup"><span data-stu-id="17a8d-151">2.1</span></span> |
| [<span data-ttu-id="17a8d-152">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="17a8d-152">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="17a8d-153">2.1</span><span class="sxs-lookup"><span data-stu-id="17a8d-153">2.1</span></span> |
| [<span data-ttu-id="17a8d-154">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="17a8d-154">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="17a8d-155">2.1</span><span class="sxs-lookup"><span data-stu-id="17a8d-155">2.1</span></span> |
| [<span data-ttu-id="17a8d-156">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="17a8d-156">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="17a8d-157">1</span><span class="sxs-lookup"><span data-stu-id="17a8d-157">1.0</span></span> |
| [<span data-ttu-id="17a8d-158">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="17a8d-158">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="17a8d-159">1</span><span class="sxs-lookup"><span data-stu-id="17a8d-159">1.0</span></span> |
| [<span data-ttu-id="17a8d-160">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="17a8d-160">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="17a8d-161">1</span><span class="sxs-lookup"><span data-stu-id="17a8d-161">1.0</span></span> |
| [<span data-ttu-id="17a8d-162">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="17a8d-162">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="17a8d-163">1</span><span class="sxs-lookup"><span data-stu-id="17a8d-163">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="17a8d-164">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-164">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="17a8d-165">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-165">.NET Core 3.0</span></span>

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

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="17a8d-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="17a8d-166">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="17a8d-167">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="17a8d-167">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
