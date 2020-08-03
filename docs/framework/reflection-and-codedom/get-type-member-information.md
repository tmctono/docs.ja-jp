---
title: '方法: リフレクションを使用して型とメンバーの情報を取得する'
description: リフレクションを使用して型とメンバーの情報を取得する方法について説明します。ここでは、System.Reflection 名前空間を使用します。
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: fa7af39c0addb328944a03236c26982301caf722
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865321"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>方法: リフレクションを使用して型とメンバーの情報を取得する
<xref:System.Reflection> 名前空間には、型とそのメンバーに関する情報を取得するための多くのメソッドがあります。 この記事では、これらのメソッドの 1 つである <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> を例として示します。 詳細については、「[リフレクションの概要](reflection.md)」を参照してください。
  
## <a name="example"></a>例

リフレクションを使用して型とメンバーの情報を取得する例を次に示します。

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>関連項目

- [アプリケーション ドメインを使用したプログラミング](../app-domains/application-domains.md#programming-with-application-domains)
- [リフレクション](reflection.md)
- [アプリケーション ドメインを使用する](../app-domains/use.md)
