---
title: 基本クラス ライブラリの破壊的変更
description: Core .NET ライブラリにおける破壊的変更の一覧を示します。
ms.date: 09/20/2019
ms.openlocfilehash: 1c56358e69d0dd6e8572a41229c1b9edbcdad795
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365618"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="9aaa0-103">Core .NET ライブラリの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="9aaa0-104">Core .NET ライブラリでは、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9aaa0-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="9aaa0-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aaa0-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="9aaa0-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="9aaa0-106">Breaking change</span></span> | <span data-ttu-id="9aaa0-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9aaa0-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="9aaa0-108">SSE および SSE2 の CompareGreaterThan メソッドで NaN 入力が正しく処理されるようになった</span><span class="sxs-lookup"><span data-stu-id="9aaa0-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="9aaa0-109">5.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-109">5.0</span></span> |
| [<span data-ttu-id="9aaa0-110">インスタンスが既に存在する場合、CounterSet.CreateCounterSetInstance は InvalidOperationException をスローするようになった</span><span class="sxs-lookup"><span data-stu-id="9aaa0-110">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="9aaa0-111">5.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-111">5.0</span></span> |
| [<span data-ttu-id="9aaa0-112">Microsoft.DotNet.PlatformAbstractions パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="9aaa0-112">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="9aaa0-113">5.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-113">5.0</span></span> |
| [<span data-ttu-id="9aaa0-114">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="9aaa0-114">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="9aaa0-115">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-115">3.0</span></span> |
| [<span data-ttu-id="9aaa0-116">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="9aaa0-116">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="9aaa0-117">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-117">3.0</span></span> |
| [<span data-ttu-id="9aaa0-118">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-118">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="9aaa0-119">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-119">3.0</span></span> |
| [<span data-ttu-id="9aaa0-120">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="9aaa0-120">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="9aaa0-121">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-121">3.0</span></span> |
| [<span data-ttu-id="9aaa0-122">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="9aaa0-122">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="9aaa0-123">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-123">3.0</span></span> |
| [<span data-ttu-id="9aaa0-124">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="9aaa0-124">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="9aaa0-125">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-125">3.0</span></span> |
| [<span data-ttu-id="9aaa0-126">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="9aaa0-126">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="9aaa0-127">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-127">3.0</span></span> |
| [<span data-ttu-id="9aaa0-128">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="9aaa0-128">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="9aaa0-129">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-129">3.0</span></span> |
| [<span data-ttu-id="9aaa0-130">JSON シリアライザーの例外の種類を JsonException から NotSupportedException に変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-130">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="9aaa0-131">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-131">3.0</span></span> |
| [<span data-ttu-id="9aaa0-132">Utf8JsonWriter での (string)null のセマンティクスの変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-132">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="9aaa0-133">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-133">3.0</span></span> |
| [<span data-ttu-id="9aaa0-134">JsonEncodedText.Encode メソッドに JavaScriptEncoder 引数を追加</span><span class="sxs-lookup"><span data-stu-id="9aaa0-134">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="9aaa0-135">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-135">3.0</span></span> |
| [<span data-ttu-id="9aaa0-136">JsonFactoryConverter.CreateConverter 署名の変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-136">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="9aaa0-137">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-137">3.0</span></span> |
| [<span data-ttu-id="9aaa0-138">JsonElement API の変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-138">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="9aaa0-139">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-139">3.0</span></span> |
| [<span data-ttu-id="9aaa0-140">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="9aaa0-140">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="9aaa0-141">3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-141">3.0</span></span> |
| [<span data-ttu-id="9aaa0-142">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="9aaa0-142">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="9aaa0-143">2.1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-143">2.1</span></span> |
| [<span data-ttu-id="9aaa0-144">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="9aaa0-144">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="9aaa0-145">2.1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-145">2.1</span></span> |
| [<span data-ttu-id="9aaa0-146">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="9aaa0-146">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="9aaa0-147">2.1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-147">2.1</span></span> |
| [<span data-ttu-id="9aaa0-148">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="9aaa0-148">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="9aaa0-149">1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-149">1.0</span></span> |
| [<span data-ttu-id="9aaa0-150">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="9aaa0-150">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="9aaa0-151">1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-151">1.0</span></span> |
| [<span data-ttu-id="9aaa0-152">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="9aaa0-152">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="9aaa0-153">1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-153">1.0</span></span> |
| [<span data-ttu-id="9aaa0-154">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="9aaa0-154">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="9aaa0-155">1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-155">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="9aaa0-156">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-156">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="9aaa0-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-157">.NET Core 3.0</span></span>

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

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

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

## <a name="net-core-21"></a><span data-ttu-id="9aaa0-158">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9aaa0-158">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="9aaa0-159">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9aaa0-159">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
