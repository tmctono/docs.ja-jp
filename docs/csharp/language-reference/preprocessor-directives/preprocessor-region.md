---
description: '#region - C# リファレンス'
title: '#region - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137943"
---
# <a name="region-c-reference"></a>#region (C# リファレンス)
`#region` を使用すると、コード ブロックを指定できます。このブロックは、コード エディターの[アウトライン](/visualstudio/ide/outlining)機能を使用して、展開や折りたたみを行うことができます。 コード ファイルが長い場合は、現在操作している部分に集中できるように 1 つ以上の領域を折りたたむ (非表示にする) ことができると便利です。 次の例では、領域を定義する方法を示します。  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Remarks  
 `#region` ブロックは、[#endregion](./preprocessor-endregion.md) ディレクティブで終了させる必要があります。  
  
 `#region` ブロックは、[#if](./preprocessor-if.md) ブロックと重複することはできません。 ただし、`#region` ブロックを `#if` ブロック内に入れ子にしたり、`#if` ブロックを `#region` ブロック内に入れ子にしたりすることはできます。  
  
## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# プリプロセッサ ディレクティブ](./index.md)
