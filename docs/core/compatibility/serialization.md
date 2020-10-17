---
title: シリアル化に関する破壊的変更
description: .NET Core と .NET 5.0 以降のシリアル化カテゴリにおける破壊的変更を一覧で示します。
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955338"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="e3fdb-103">シリアル化に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="e3fdb-103">Serialization breaking changes</span></span>

<span data-ttu-id="e3fdb-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3fdb-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e3fdb-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="e3fdb-105">Breaking change</span></span> | <span data-ttu-id="e3fdb-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e3fdb-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="e3fdb-107">型パラメーターが null の場合に JsonSerializer.Serialize によって ArgumentNullException がスローされる</span><span class="sxs-lookup"><span data-stu-id="e3fdb-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="e3fdb-108">5.0</span><span class="sxs-lookup"><span data-stu-id="e3fdb-108">5.0</span></span> |
| [<span data-ttu-id="e3fdb-109">JsonSerializer.Deserialize によって 1 文字の文字列が求められる</span><span class="sxs-lookup"><span data-stu-id="e3fdb-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="e3fdb-110">5.0</span><span class="sxs-lookup"><span data-stu-id="e3fdb-110">5.0</span></span> |
| [<span data-ttu-id="e3fdb-111">BinaryFormatter.Deserialize によって SerializationException の例外の一部が再ラップされる</span><span class="sxs-lookup"><span data-stu-id="e3fdb-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="e3fdb-112">5.0</span><span class="sxs-lookup"><span data-stu-id="e3fdb-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e3fdb-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e3fdb-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
