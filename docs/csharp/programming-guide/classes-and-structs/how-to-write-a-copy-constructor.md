---
title: '方法: コピー コンストラクターを記述する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: bdc352566052f4cec1686176131e9b1e1b768794
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596607"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="9768a-102">方法: コピー コンストラクターを記述する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9768a-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="9768a-103">C# では、オブジェクトのコピー コンストラクターが提供されていませんが、独自に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9768a-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9768a-104">例</span><span class="sxs-lookup"><span data-stu-id="9768a-104">Example</span></span>  
 <span data-ttu-id="9768a-105">次の例の `Person` [クラス](../../language-reference/keywords/class.md)では、`Person` のインスタンスを引数として受け取るコピー コンストラクターが定義されています。</span><span class="sxs-lookup"><span data-stu-id="9768a-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="9768a-106">引数のプロパティの値は、`Person`の新しいインスタンスのプロパティに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9768a-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="9768a-107">このコードには、コピーするインスタンスの `Name` プロパティと `Age` プロパティをクラスのインスタンス コンストラクターに渡す代替のコピー コンストラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9768a-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="9768a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9768a-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="9768a-109">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="9768a-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9768a-110">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="9768a-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="9768a-111">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="9768a-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="9768a-112">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="9768a-112">Finalizers</span></span>](./destructors.md)
