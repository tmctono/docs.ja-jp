---
title: 基本クラス ライブラリの破壊的変更
description: 基本クラス ライブラリである .NET CoreFx での破壊的変更の一覧を示します。
ms.date: 09/20/2019
ms.openlocfilehash: 56a3cf4f4c00a79752d5a98bb086bb9f8c0614b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147576"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="45855-103">CoreFx に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="45855-103">CoreFx breaking changes</span></span>

<span data-ttu-id="45855-104">CoreFx では、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="45855-104">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="45855-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="45855-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="45855-106">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="45855-106">Breaking change</span></span> | <span data-ttu-id="45855-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="45855-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="45855-108">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになった</span><span class="sxs-lookup"><span data-stu-id="45855-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="45855-109">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-109">3.0</span></span> |
| [<span data-ttu-id="45855-110">カスタム EncoderFallbackBuffer インスタンスが再帰的にフォールバックしない</span><span class="sxs-lookup"><span data-stu-id="45855-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="45855-111">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-111">3.0</span></span> |
| [<span data-ttu-id="45855-112">浮動小数点の書式設定と解析の動作の変更</span><span class="sxs-lookup"><span data-stu-id="45855-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="45855-113">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-113">3.0</span></span> |
| [<span data-ttu-id="45855-114">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="45855-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="45855-115">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-115">3.0</span></span> |
| [<span data-ttu-id="45855-116">InvalidAsynchronousStateException を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="45855-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="45855-117">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-117">3.0</span></span> |
| [<span data-ttu-id="45855-118">.NET Core 3.0 は不正な形式の UTF-8 バイト シーケンスを置換するときに Unicode のベスト プラクティスに従う</span><span class="sxs-lookup"><span data-stu-id="45855-118">NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | <span data-ttu-id="45855-119">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-119">3.0</span></span> |
| [<span data-ttu-id="45855-120">TypeDescriptionProviderAttribute を別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="45855-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="45855-121">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-121">3.0</span></span> |
| [<span data-ttu-id="45855-122">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="45855-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="45855-123">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-123">3.0</span></span> |
| [<span data-ttu-id="45855-124">JSON シリアライザーの例外の種類を JsonException から NotSupportedException に変更</span><span class="sxs-lookup"><span data-stu-id="45855-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="45855-125">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-125">3.0</span></span> |
| [<span data-ttu-id="45855-126">Utf8JsonWriter での (string)null のセマンティクスの変更</span><span class="sxs-lookup"><span data-stu-id="45855-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="45855-127">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-127">3.0</span></span> |
| [<span data-ttu-id="45855-128">JsonEncodedText.Encode メソッドに JavaScriptEncoder 引数を追加</span><span class="sxs-lookup"><span data-stu-id="45855-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="45855-129">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-129">3.0</span></span> |
| [<span data-ttu-id="45855-130">JsonFactoryConverter.CreateConverter 署名の変更</span><span class="sxs-lookup"><span data-stu-id="45855-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="45855-131">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-131">3.0</span></span> |
| [<span data-ttu-id="45855-132">JsonElement API の変更</span><span class="sxs-lookup"><span data-stu-id="45855-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="45855-133">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-133">3.0</span></span> |
| [<span data-ttu-id="45855-134">FieldInfo.SetValue で、静的な初期化専用フィールドに対する例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="45855-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="45855-135">3.0</span><span class="sxs-lookup"><span data-stu-id="45855-135">3.0</span></span> |
| [<span data-ttu-id="45855-136">組み込みの構造体型に追加されたプライベート フィールド</span><span class="sxs-lookup"><span data-stu-id="45855-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="45855-137">2.1</span><span class="sxs-lookup"><span data-stu-id="45855-137">2.1</span></span> |
| [<span data-ttu-id="45855-138">UseShellExecute の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="45855-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="45855-139">2.1</span><span class="sxs-lookup"><span data-stu-id="45855-139">2.1</span></span> |
| [<span data-ttu-id="45855-140">macOS 上の OpenSSL バージョン</span><span class="sxs-lookup"><span data-stu-id="45855-140">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="45855-141">2.1</span><span class="sxs-lookup"><span data-stu-id="45855-141">2.1</span></span> |
| [<span data-ttu-id="45855-142">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="45855-142">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="45855-143">1</span><span class="sxs-lookup"><span data-stu-id="45855-143">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="45855-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="45855-144">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="45855-145">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="45855-145">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="45855-146">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="45855-146">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
