---
title: 基本クラス ライブラリの破壊的変更
description: Core .NET ライブラリにおける破壊的変更の一覧を示します。
ms.date: 09/20/2019
ms.openlocfilehash: ca50123b842c256607d47010dbef9b216ece4661
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420431"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="5b900-103">Core .NET ライブラリの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="5b900-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="5b900-104">Core .NET ライブラリでは、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5b900-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="5b900-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b900-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="5b900-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="5b900-106">Breaking change</span></span> | <span data-ttu-id="5b900-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="5b900-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="5b900-108">SSE および SSE2 の CompareGreaterThan メソッドで NaN 入力が正しく処理されるようになった</span><span class="sxs-lookup"><span data-stu-id="5b900-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="5b900-109">5.0</span><span class="sxs-lookup"><span data-stu-id="5b900-109">5.0</span></span> |
| [<span data-ttu-id="5b900-110">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="5b900-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="5b900-111">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-111">3.0</span></span> |
| [<span data-ttu-id="5b900-112">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="5b900-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="5b900-113">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-113">3.0</span></span> |
| [<span data-ttu-id="5b900-114">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="5b900-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="5b900-115">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-115">3.0</span></span> |
| [<span data-ttu-id="5b900-116">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="5b900-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="5b900-117">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-117">3.0</span></span> |
| [<span data-ttu-id="5b900-118">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="5b900-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="5b900-119">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-119">3.0</span></span> |
| [<span data-ttu-id="5b900-120">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="5b900-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="5b900-121">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-121">3.0</span></span> |
| [<span data-ttu-id="5b900-122">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="5b900-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="5b900-123">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-123">3.0</span></span> |
| [<span data-ttu-id="5b900-124">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="5b900-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="5b900-125">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-125">3.0</span></span> |
| [<span data-ttu-id="5b900-126">JSON シリアライザーの例外の種類を JsonException から NotSupportedException に変更</span><span class="sxs-lookup"><span data-stu-id="5b900-126">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="5b900-127">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-127">3.0</span></span> |
| [<span data-ttu-id="5b900-128">Utf8JsonWriter での (string)null のセマンティクスの変更</span><span class="sxs-lookup"><span data-stu-id="5b900-128">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="5b900-129">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-129">3.0</span></span> |
| [<span data-ttu-id="5b900-130">JsonEncodedText.Encode メソッドに JavaScriptEncoder 引数を追加</span><span class="sxs-lookup"><span data-stu-id="5b900-130">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="5b900-131">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-131">3.0</span></span> |
| [<span data-ttu-id="5b900-132">JsonFactoryConverter.CreateConverter 署名の変更</span><span class="sxs-lookup"><span data-stu-id="5b900-132">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="5b900-133">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-133">3.0</span></span> |
| [<span data-ttu-id="5b900-134">JsonElement API の変更</span><span class="sxs-lookup"><span data-stu-id="5b900-134">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="5b900-135">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-135">3.0</span></span> |
| [<span data-ttu-id="5b900-136">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="5b900-136">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="5b900-137">3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-137">3.0</span></span> |
| [<span data-ttu-id="5b900-138">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="5b900-138">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="5b900-139">2.1</span><span class="sxs-lookup"><span data-stu-id="5b900-139">2.1</span></span> |
| [<span data-ttu-id="5b900-140">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="5b900-140">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="5b900-141">2.1</span><span class="sxs-lookup"><span data-stu-id="5b900-141">2.1</span></span> |
| [<span data-ttu-id="5b900-142">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="5b900-142">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="5b900-143">2.1</span><span class="sxs-lookup"><span data-stu-id="5b900-143">2.1</span></span> |
| [<span data-ttu-id="5b900-144">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="5b900-144">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="5b900-145">1</span><span class="sxs-lookup"><span data-stu-id="5b900-145">1.0</span></span> |
| [<span data-ttu-id="5b900-146">プロセス破損状態例外の処理がサポートされない</span><span class="sxs-lookup"><span data-stu-id="5b900-146">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="5b900-147">1</span><span class="sxs-lookup"><span data-stu-id="5b900-147">1.0</span></span> |
| [<span data-ttu-id="5b900-148">UriBuilder のプロパティでは今後、先頭に文字が付加されない</span><span class="sxs-lookup"><span data-stu-id="5b900-148">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="5b900-149">1</span><span class="sxs-lookup"><span data-stu-id="5b900-149">1.0</span></span> |
| [<span data-ttu-id="5b900-150">開始されなかったプロセスについて Process.StartInfo が InvalidOperationException をスローする</span><span class="sxs-lookup"><span data-stu-id="5b900-150">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="5b900-151">1</span><span class="sxs-lookup"><span data-stu-id="5b900-151">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="5b900-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5b900-152">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="5b900-153">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5b900-153">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="5b900-154">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b900-154">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="5b900-155">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="5b900-155">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
