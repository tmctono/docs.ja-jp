---
title: CoreFx に関する破壊的変更 - .NET Core
description: 基本クラス ライブラリである .NET CoreFx での破壊的変更の一覧を示します。
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7681dadbbbae737cb1cbc260613baea9d34527a8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002439"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="cc05e-103">CoreFx に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="cc05e-103">CoreFx breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc05e-104">この記事は作成中です。</span><span class="sxs-lookup"><span data-stu-id="cc05e-104">This article is under construction.</span></span> <span data-ttu-id="cc05e-105">これは、.NET Core の破壊的変更の完全なリストではありません。</span><span class="sxs-lookup"><span data-stu-id="cc05e-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="cc05e-106">.NET Core の破壊的変更の詳細については、GitHub の dotnet/docs リポジトリで個別の[破壊的変更の問題](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)について調べてください。</span><span class="sxs-lookup"><span data-stu-id="cc05e-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="cc05e-107">.NET Core のバージョンごとに CoreFx に関する破壊的変更の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cc05e-107">The following is a list of CoreFx breaking changes by .NET Core version.</span></span> <span data-ttu-id="cc05e-108">CoreFx では、.NET Core で使用されるプリミティブとその他の一般的な型が提供されます。</span><span class="sxs-lookup"><span data-stu-id="cc05e-108">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

## <a name="net-core-30-preview-7"></a><span data-ttu-id="cc05e-109">.NET Core 3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="cc05e-109">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/jsonelement-api-changes.md)]

## <a name="net-core-30-preview-8"></a><span data-ttu-id="cc05e-110">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="cc05e-110">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/jsonfactoryconverter-createconverter.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="cc05e-111">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="cc05e-111">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Json serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/serializer-throws-notsupportedexception.md)]

## <a name="net-core-30"></a><span data-ttu-id="cc05e-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cc05e-112">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]
