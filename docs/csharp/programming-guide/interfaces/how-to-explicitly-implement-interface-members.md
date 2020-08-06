---
title: インターフェイス メンバーを明示的に実装する方法 - C# プログラミング ガイド
description: この C# の例では、インターフェイス メンバーを明示的に実装する方法について説明します。 メンバーには、インターフェイス インスタンスを介してアクセスします。
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303076"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>インターフェイス メンバーを明示的に実装する方法 (C# プログラミング ガイド)
この例では[インターフェイス](../../language-reference/keywords/interface.md)、`IDimensions`、およびクラス `Box` を宣言します。これは、インターフェイス メンバーの `GetLength` と `GetWidth` を明示的に実装します。 メンバーには、インターフェイス インスタンス `dimensions` を介してアクセスします。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
  
- `Main` メソッドでは、次の行はコメントアウトされます。これらの行でコンパイル エラーが発生するためです。 明示的に実装されるインターフェイス メンバーに、[クラス](../../language-reference/keywords/class.md) インスタンスからアクセスすることはできません。  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- `Main` メソッドの以下の行では、メソッドがインターフェイスのインスタンスから呼び出されるため、ボックスのサイズを正常に出力できます。  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [クラスと構造体](../classes-and-structs/index.md)
- [インターフェイス](./index.md)
- [2 つのインターフェイスのメンバーを明示的に実装する方法](./how-to-explicitly-implement-members-of-two-interfaces.md)
