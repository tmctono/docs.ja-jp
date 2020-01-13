---
title: コピー コンストラクターを記述する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714851"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="c33e4-102">コピー コンストラクターを記述する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c33e4-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="c33e4-103">C# では、オブジェクトのコピー コンストラクターが提供されていませんが、独自に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c33e4-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c33e4-104">例</span><span class="sxs-lookup"><span data-stu-id="c33e4-104">Example</span></span>  
 <span data-ttu-id="c33e4-105">次の例の `Person`[クラス](../../language-reference/keywords/class.md)では、`Person` のインスタンスを引数として受け取るコピー コンストラクターが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c33e4-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="c33e4-106">引数のプロパティの値は、`Person`の新しいインスタンスのプロパティに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c33e4-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="c33e4-107">このコードには、コピーするインスタンスの `Name` プロパティと `Age` プロパティをクラスのインスタンス コンストラクターに渡す代替のコピー コンストラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c33e4-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="c33e4-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="c33e4-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="c33e4-109">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c33e4-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c33e4-110">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="c33e4-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="c33e4-111">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="c33e4-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="c33e4-112">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="c33e4-112">Finalizers</span></span>](./destructors.md)
