---
title: コンテキスト キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 03/07/2017
helpviewer_keywords:
- contextual keywords [C#]
ms.assetid: 7c76bc29-a754-4389-b0ab-f6b441018298
ms.openlocfilehash: 9197ebb1fa48011c60a6d224497e57a604870fc3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422869"
---
# <a name="contextual-keywords-c-reference"></a><span data-ttu-id="be056-102">コンテキスト キーワード (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="be056-102">Contextual Keywords (C# Reference)</span></span>

<span data-ttu-id="be056-103">コンテキスト キーワードを使用して、コード内で特定の意味を付与することができます。ただし C# ではコンテキスト キーワードは予約語ではありません。</span><span class="sxs-lookup"><span data-stu-id="be056-103">A contextual keyword is used to provide a specific meaning in the code, but it is not a reserved word in C#.</span></span> <span data-ttu-id="be056-104">このセクションでは、次のコンテキスト キーワードを紹介します。</span><span class="sxs-lookup"><span data-stu-id="be056-104">The following contextual keywords are introduced in this section:</span></span>  
  
|<span data-ttu-id="be056-105">キーワード</span><span class="sxs-lookup"><span data-stu-id="be056-105">Keyword</span></span>|<span data-ttu-id="be056-106">説明</span><span class="sxs-lookup"><span data-stu-id="be056-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be056-107">add</span><span class="sxs-lookup"><span data-stu-id="be056-107">add</span></span>](./add.md)|<span data-ttu-id="be056-108">クライアント コードがイベントをサブスクライブするときに呼び出されるカスタム イベント アクセサーを定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-108">Defines a custom event accessor that is invoked when client code subscribes to the event.</span></span>|  
|[<span data-ttu-id="be056-109">async</span><span class="sxs-lookup"><span data-stu-id="be056-109">async</span></span>](./async.md)|<span data-ttu-id="be056-110">修飾されたメソッド、ラムダ式、または匿名メソッドが非同期であることを示します。</span><span class="sxs-lookup"><span data-stu-id="be056-110">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="be056-111">await</span><span class="sxs-lookup"><span data-stu-id="be056-111">await</span></span>](../operators/await.md)|<span data-ttu-id="be056-112">待機中のタスクが完了するまで async のメソッドを中断します。</span><span class="sxs-lookup"><span data-stu-id="be056-112">Suspends an async method until an awaited task is completed.</span></span>|  
|[<span data-ttu-id="be056-113">dynamic</span><span class="sxs-lookup"><span data-stu-id="be056-113">dynamic</span></span>](../builtin-types/reference-types.md)|<span data-ttu-id="be056-114">コンパイル時の型チェックをバイパスする処理を可能にする参照型を定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-114">Defines a reference type that enables operations in which it occurs to bypass compile-time type checking.</span></span>|  
|[<span data-ttu-id="be056-115">get</span><span class="sxs-lookup"><span data-stu-id="be056-115">get</span></span>](./get.md)|<span data-ttu-id="be056-116">プロパティまたはインデクサーのアクセサー メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-116">Defines an accessor method for a property or an indexer.</span></span>|  
|[<span data-ttu-id="be056-117">global</span><span class="sxs-lookup"><span data-stu-id="be056-117">global</span></span>](../operators/namespace-alias-qualifier.md)|<span data-ttu-id="be056-118">グローバル名前空間のエイリアス (それ以外の場合は無名です)。</span><span class="sxs-lookup"><span data-stu-id="be056-118">Alias of the global namespace, which is otherwise unnamed.</span></span>|  
|[<span data-ttu-id="be056-119">partial</span><span class="sxs-lookup"><span data-stu-id="be056-119">partial</span></span>](./partial-type.md)|<span data-ttu-id="be056-120">同一コンパイル ユニットに部分クラス、部分構造体、または部分インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-120">Defines partial classes, structs, and interfaces throughout the same compilation unit.</span></span>|  
|[<span data-ttu-id="be056-121">remove</span><span class="sxs-lookup"><span data-stu-id="be056-121">remove</span></span>](./remove.md)|<span data-ttu-id="be056-122">クライアント コードがイベントのサブスクライブを解除するときに呼び出されるカスタム イベント アクセサーを定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-122">Defines a custom event accessor that is invoked when client code unsubscribes from the event.</span></span>|  
|[<span data-ttu-id="be056-123">set</span><span class="sxs-lookup"><span data-stu-id="be056-123">set</span></span>](./set.md)|<span data-ttu-id="be056-124">プロパティまたはインデクサーのアクセサー メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="be056-124">Defines an accessor method for a property or an indexer.</span></span>|  
|[<span data-ttu-id="be056-125">value</span><span class="sxs-lookup"><span data-stu-id="be056-125">value</span></span>](./value.md)|<span data-ttu-id="be056-126">アクセサーを設定したり、イベント ハンドラーを追加または削除したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="be056-126">Used to set accessors and to add or remove event handlers.</span></span>|  
|[<span data-ttu-id="be056-127">var</span><span class="sxs-lookup"><span data-stu-id="be056-127">var</span></span>](./var.md)|<span data-ttu-id="be056-128">メソッド スコープで宣言された変数の型をコンパイラで判断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="be056-128">Enables the type of a variable declared at method scope to be determined by the compiler.</span></span>|  
|[<span data-ttu-id="be056-129">when</span><span class="sxs-lookup"><span data-stu-id="be056-129">when</span></span>](when.md)|<span data-ttu-id="be056-130">`catch` ブロックまたは `switch` ステートメントの `case` ラベルのフィルター条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="be056-130">Specifies a filter condition for a `catch` block or the `case` label of a `switch` statement.</span></span>|
|[<span data-ttu-id="be056-131">where</span><span class="sxs-lookup"><span data-stu-id="be056-131">where</span></span>](./where-generic-type-constraint.md)|<span data-ttu-id="be056-132">ジェネリック宣言に制約を追加します</span><span class="sxs-lookup"><span data-stu-id="be056-132">Adds constraints to a generic declaration.</span></span> <span data-ttu-id="be056-133">(「[where](./where-clause.md)」も参照してください)。</span><span class="sxs-lookup"><span data-stu-id="be056-133">(See also [where](./where-clause.md)).</span></span>|  
|[<span data-ttu-id="be056-134">yield</span><span class="sxs-lookup"><span data-stu-id="be056-134">yield</span></span>](./yield.md)|<span data-ttu-id="be056-135">反復子ブロックで使用され、列挙子オブジェクトに値を返すか、反復処理の終了を通知します。</span><span class="sxs-lookup"><span data-stu-id="be056-135">Used in an iterator block to return a value to the enumerator object or to signal the end of iteration.</span></span>|  
  
 <span data-ttu-id="be056-136">C# 3.0 で導入されたすべてのクエリ キーワードもコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="be056-136">All query keywords introduced in C# 3.0 are also contextual.</span></span> <span data-ttu-id="be056-137">詳細については「[クエリ キーワード (LINQ)](./query-keywords.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be056-137">For more information, see [Query Keywords (LINQ)](./query-keywords.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be056-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="be056-138">See also</span></span>

- [<span data-ttu-id="be056-139">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="be056-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="be056-140">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="be056-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="be056-141">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="be056-141">C# Keywords</span></span>](./index.md)
