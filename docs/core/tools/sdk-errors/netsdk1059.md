---
title: NETSDK1059:プロジェクトに古い .NET CLI ツールが含まれています
description: プロジェクトに古い .NET CLI ツールが含まれている問題を解決する方法。
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957100"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059:プロジェクトに古い .NET CLI ツールが含まれています

**この記事の対象:**  ✔️ .NET 2.1.100 SDK 以降のバージョン

.NET SDK によって警告 NETSDK1059 が発行される場合、プロジェクトには古い .NET CLI ツールが含まれています。 .NET 2.1 では、これらのツールは .NET SDK に含まれており、プロジェクトによって明示的に参照される必要はありません。 .NET 2.1 への移行の詳細については、[こちら](https://aka.ms/dotnetclitools-in-box)を参照してください。
