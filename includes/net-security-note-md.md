---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224354"
---
> [!CAUTION]
> コードアクセスセキュリティ (CAS) と部分信頼コード
>
> .NET Framework には、コード アクセス セキュリティ (CAS) と呼ばれる、同一アプリケーションで実行される各種コードにさまざまな信頼レベルを強制的に適用するメカニズムが備わっています。
>
> **CAS は、.NET Core、.NET 5、またはそれ以降のバージョンではサポートされていません。CAS は、7.0 より後のバージョンの C# ではサポートされていません。**
>
> .NET Framework の CA は、コードの作成やその他の id の側面に基づいてセキュリティ境界を適用するためのメカニズムとして使用しないでください。 CA と Security-Transparent コードは、部分的に信頼されたコード、特に不明な配信元のコードを含むセキュリティ境界としてはサポートされません。 発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。 .NET Framework は、CA サンドボックスに対して検出される可能性がある昇格した特権の悪用に対して、セキュリティ更新プログラムを発行しません。
>
> このポリシーは .NET Framework のすべてのバージョンに適用されますが、Silverlight に含まれる .NET Framework には適用されません。
