---
title: シリアル化に関する破壊的変更
description: .NET Core と .NET 5.0 以降のシリアル化カテゴリにおける破壊的変更を一覧で示します。
ms.date: 07/30/2020
ms.openlocfilehash: f635ff2cd233922a0bbb327de23c8bf25d344fa0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517410"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="9097f-103">シリアル化に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="9097f-103">Serialization breaking changes</span></span>

<span data-ttu-id="9097f-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="9097f-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="9097f-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="9097f-105">Breaking change</span></span> | <span data-ttu-id="9097f-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9097f-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="9097f-107">BinaryFormatter.Deserialize によって SerializationException の例外の一部が再ラップされる</span><span class="sxs-lookup"><span data-stu-id="9097f-107">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="9097f-108">5.0</span><span class="sxs-lookup"><span data-stu-id="9097f-108">5.0</span></span> |

## <a name="net-core-50"></a><span data-ttu-id="9097f-109">.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="9097f-109">.NET Core 5.0</span></span>

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
