---
description: remove コンテキスト キーワード - C# リファレンス
title: remove コンテキスト キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: a5514e72a04daa1232dbdf9a37813f09de791590
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136955"
---
# <a name="remove-c-reference"></a>remove (C# リファレンス)

`remove` コンテキスト キーワードは、カスタム イベント アクセサーを定義するときに使用されます。このアクセサーは、クライアント コードが[イベント](event.md)から登録を解除するときに呼び出されます。 カスタムの `remove` アクセサーを指定するときは、[add](add.md) アクセサーも指定する必要があります。

## <a name="example"></a>例

次の例は、カスタムの [add](add.md) アクセサーと `remove` アクセサーが指定されているイベントを示しています。 サンプル全体については、「[インターフェイス イベントを実装する方法](../../programming-guide/events/how-to-implement-interface-events.md)」を参照してください。

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

通常は、独自のカスタム イベント アクセサーを提供する必要はありません。 イベントを宣言するときにコンパイラで自動生成されるアクセサーは、ほとんどのシナリオで利用することができます。

## <a name="see-also"></a>関連項目

- [イベント](../../programming-guide/events/index.md)
