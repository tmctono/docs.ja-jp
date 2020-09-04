---
description: C# で add キーワードを使用してカスタム イベント アクセサーを作成する方法について説明する
title: add - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 520267574320af7f85f2ee07e2778f8bebd01e4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127010"
---
# <a name="add-c-reference"></a>add (C# リファレンス)
`add` コンテキスト キーワードは、カスタム イベント アクセサーを定義するときに使用されます。このアクセサーは、クライアント コードが[イベント](./event.md)をサブスクライブするときに呼び出されます。 カスタムの `add` アクセサーを指定するときは、[remove](./remove.md) アクセサーも指定する必要があります。  
  
## <a name="example"></a>例  
次の例は、カスタムの `add` アクセサーと [remove](./remove.md) アクセサーが指定されているイベントを示しています。 サンプル全体については、「[インターフェイス イベントを実装する方法](../../programming-guide/events/how-to-implement-interface-events.md)」を参照してください。
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 通常は、独自のカスタム イベント アクセサーを提供する必要はありません。 イベントを宣言するときにコンパイラで自動生成されるアクセサーは、ほとんどのシナリオで利用することができます。  
  
## <a name="see-also"></a>関連項目

- [イベント](../../programming-guide/events/index.md)
