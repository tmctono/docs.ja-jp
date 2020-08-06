---
title: デリゲートを結合する方法 (マルチキャスト デリゲート) - C# プログラミング ガイド
description: デリゲートを結合してマルチキャスト デリゲートを作成する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302738"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>デリゲートを結合する方法 (マルチキャスト デリゲート) (C# プログラミング ガイド)
ここでは、マルチキャスト デリゲートを作成する例について説明します。 [デリゲート](../../language-reference/builtin-types/reference-types.md) オブジェクトの便利な性質の 1 つは、`+` 演算子を使用して、複数のオブジェクトを 1 つのデリゲート インスタンスに割り当てられることです。 マルチキャスト デリゲートには、割り当てられたデリゲートの一覧が含まれています。 マルチキャスト デリゲートを呼び出すと、一覧内のデリゲートが順に呼び出されます。 結合できるのは、同じ型のデリゲートのみです。  
  
 `-` 演算子を使用して、マルチキャスト デリゲートからコンポーネント デリゲートを削除することができます。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.MulticastDelegate>
- [C# プログラミング ガイド](../index.md)
- [イベント](../events/index.md)
