---
title: Property Let プロシージャが定義されておらず、Property Get プロシージャからオブジェクトが返されませんでした。
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871094"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Property Let プロシージャが定義されておらず、Property Get プロシージャからオブジェクトが返されませんでした。

特定のプロパティ、メソッド、および操作は、`Collection` オブジェクトにのみ適用できます。 コレクション専用の操作またはプロパティを指定しましたが、このオブジェクトはコレクションではありません。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. オブジェクトまたはプロパティ名のスペルを確認するか、オブジェクトが `Collection` オブジェクトであることを確認します。  
  
2. オブジェクトをコレクションに追加するために使用する `Add` メソッドを確認して、構文が正しいことと、識別子のスペルが正しいことを確認します。  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.Collection>
