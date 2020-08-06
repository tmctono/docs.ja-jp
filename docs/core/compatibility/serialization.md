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
# <a name="serialization-breaking-changes"></a>シリアル化に関する破壊的変更

このページでは、次の破壊的変更について説明します。

| 互換性に影響する変更点 | 導入されたバージョン |
| - | - |
| [BinaryFormatter.Deserialize によって SerializationException の例外の一部が再ラップされる](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-core-50"></a>.NET Core 5.0

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
