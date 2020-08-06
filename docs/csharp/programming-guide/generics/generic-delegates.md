---
title: 汎用デリゲート - C# プログラミング ガイド
description: C# で汎用デリゲートを使用する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: d99271ca9f12e95743d633caac16aaa4151e9c41
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301906"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="d32f1-104">汎用デリゲート (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d32f1-104">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="d32f1-105">[デリゲート](../../language-reference/builtin-types/reference-types.md)はその独自の型パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d32f1-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="d32f1-106">ジェネリック デリゲートを参照するコードは、次の例に示すように、ジェネリック クラスをインスタンス化したり、ジェネリック メソッドを呼び出したりするときのように、型引数を指定し、構築されたクローズ型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d32f1-106">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="d32f1-107">C# バージョン 2.0 には、メソッド グループ変換という新しい機能があります。これはジェネリック デリゲート型だけでなく具象型にも適用され、前の行を次のような簡素化された構文で記述できます。</span><span class="sxs-lookup"><span data-stu-id="d32f1-107">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="d32f1-108">ジェネリック クラス内で定義されたデリゲートは、クラス メソッドと同様の方法でジェネリック クラスの型パラメーターを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d32f1-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="d32f1-109">デリゲートを参照するコードで、次のように、包含クラスの型引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d32f1-109">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="d32f1-110">ジェネリック デリゲートは、典型的な設計パターンに基づいてイベントを定義する場合に特に便利です。sender 引数は厳密に型指定できること、<xref:System.Object> との間でキャストが必要ないことがその理由です。</span><span class="sxs-lookup"><span data-stu-id="d32f1-110">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="d32f1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d32f1-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="d32f1-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d32f1-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d32f1-113">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="d32f1-113">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="d32f1-114">ジェネリック メソッド</span><span class="sxs-lookup"><span data-stu-id="d32f1-114">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="d32f1-115">ジェネリック クラス</span><span class="sxs-lookup"><span data-stu-id="d32f1-115">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="d32f1-116">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d32f1-116">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="d32f1-117">デリゲート</span><span class="sxs-lookup"><span data-stu-id="d32f1-117">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="d32f1-118">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="d32f1-118">Generics</span></span>](../../../standard/generics/index.md)
