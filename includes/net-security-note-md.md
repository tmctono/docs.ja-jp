---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855668"
---
> [!CAUTION]
> コードアクセスセキュリティ (CAS) と部分信頼コード
>
> .NET Framework には、コード アクセス セキュリティ (CAS) と呼ばれる、同一アプリケーションで実行される各種コードにさまざまな信頼レベルを強制的に適用するメカニズムが備わっています。
>
> **CAS は、.NET Core、.NET 5、またはそれ以降のバージョンではサポートされていません。CAS は、7.0 より後のバージョンの C# ではサポートされていません。**
>
> .NET Framework の CA は、コードの作成やその他の id の側面に基づいてセキュリティ境界を適用するためのメカニズムとして使用しないでください。 CA とセキュリティ透過的なコードは、部分的に信頼されたコード、特に不明なオリジンコードを含むセキュリティ境界としてはサポートされません。 発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。
>
> このポリシーは .NET Framework のすべてのバージョンに適用されますが、Silverlight に含まれる .NET Framework には適用されません。
