---
title: End <keyword> ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343733"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="3c880-102">End \<keyword > ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c880-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="3c880-103">その後に追加のキーワードが続くと、は、そのキーワードによって導入されたステートメントブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="3c880-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c880-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c880-104">Syntax</span></span>

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="3c880-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="3c880-105">Parts</span></span>

|<span data-ttu-id="3c880-106">要素</span><span class="sxs-lookup"><span data-stu-id="3c880-106">Part</span></span>|<span data-ttu-id="3c880-107">説明</span><span class="sxs-lookup"><span data-stu-id="3c880-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="3c880-108">必須。</span><span class="sxs-lookup"><span data-stu-id="3c880-108">Required.</span></span> <span data-ttu-id="3c880-109">プログラミング要素の定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="3c880-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="3c880-110">カスタムの [Event ステートメント](event-statement.md)で、対応する `AddHandler` ステートメントによって開始された `AddHandler` アクセサを終了する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="3c880-111">一致する[クラスステートメント](class-statement.md)によって開始されたクラス定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="3c880-112">一致する列挙[ステートメント](enum-statement.md)によって開始された列挙型定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="3c880-113">一致する[イベントステートメント](event-statement.md)によって開始された `Custom` イベント定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="3c880-114">一致する[Function ステートメント](function-statement.md)によって開始された `Function` プロシージャ定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="3c880-115">実行時に `End Function` ステートメントが発生すると、呼び出し元のコードに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c880-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="3c880-116">一致する[Get ステートメント](get-statement.md)によって開始された `Property` プロシージャ定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="3c880-117">実行時に `End Get` ステートメントが発生すると、プロパティの値を要求するステートメントに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c880-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="3c880-118">一致する `If` ステートメントによって開始された `If`...`Then``Else` ブロック定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="3c880-119">参照してください.. [.そうしたら。。。Else ステートメント](if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3c880-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="3c880-120">一致する[インターフェイスステートメント](interface-statement.md)によって開始されたインターフェイス定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="3c880-121">一致する[モジュールステートメント](module-statement.md)によって開始されたモジュール定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="3c880-122">一致する [Namespace ステートメント](namespace-statement.md)で開始された名前空間定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="3c880-123">一致する[Operator ステートメント](operator-statement.md)によって開始された演算子定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="3c880-124">一致する[プロパティステートメント](property-statement.md)によって開始されたプロパティ定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="3c880-125">カスタム[イベントステートメント](event-statement.md)内の一致する `RaiseEvent` ステートメントによって開始された `RaiseEvent` アクセサーを終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="3c880-126">カスタム[イベントステートメント](event-statement.md)内の一致する `RemoveHandler` ステートメントによって開始された `RemoveHandler` アクセサーを終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="3c880-127">一致する `Select` ステートメントによって開始された `Select`...`Case` ブロック定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="3c880-128">参照してください.. [.Case ステートメント](select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3c880-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="3c880-129">一致する[Set ステートメント](set-statement.md)によって開始される `Property` プロシージャの定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="3c880-130">実行時に `End Set` ステートメントが発生した場合、プロパティの値を設定するステートメントに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c880-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="3c880-131">一致する[構造ステートメント](structure-statement.md)によって開始された構造体定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="3c880-132">一致する[サブステートメント](sub-statement.md)によって開始された `Sub` プロシージャ定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="3c880-133">実行時に `End Sub` ステートメントが発生すると、呼び出し元のコードに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c880-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="3c880-134">一致する `SyncLock` ステートメントによって開始された `SyncLock` ブロック定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="3c880-135">「 [SyncLock ステートメント](synclock-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c880-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="3c880-136">一致する `Try` ステートメントによって開始された `Try`...`Catch``Finally` ブロック定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="3c880-137">[試してみる...キャッチ...Finally ステートメント](try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3c880-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="3c880-138">一致する `While` ステートメントによって開始された `While` ループ定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="3c880-139">しばらくお待ちください.. [.End While ステートメント](while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3c880-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="3c880-140">一致する `With` ステートメントによって開始された `With` ブロック定義を終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="3c880-141">参照[してください...End With ステートメント](with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3c880-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="3c880-142">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3c880-142">Directives</span></span>

<span data-ttu-id="3c880-143">先頭に番号記号 (`#`) がある場合、`End` キーワードは、対応するディレクティブによって導入された前処理ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="3c880-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="3c880-144">要素</span><span class="sxs-lookup"><span data-stu-id="3c880-144">Part</span></span>|<span data-ttu-id="3c880-145">説明</span><span class="sxs-lookup"><span data-stu-id="3c880-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="3c880-146">必須。</span><span class="sxs-lookup"><span data-stu-id="3c880-146">Required.</span></span> <span data-ttu-id="3c880-147">プリプロセスブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="3c880-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="3c880-148">一致する[#ExternalSource ディレクティブ](../directives/externalsource-directive.md)で開始された外部ソースブロックを終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="3c880-149">一致する `#If` ディレクティブで開始された条件付きコンパイルブロックを終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="3c880-150">#If を参照してください.. [.次に、ディレクティブ #Else](../directives/if-then-else-directives.md)ます。</span><span class="sxs-lookup"><span data-stu-id="3c880-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="3c880-151">一致する[#Region ディレクティブ](../directives/region-directive.md)で開始されたソースリージョンブロックを終了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3c880-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="3c880-152">コメント</span><span class="sxs-lookup"><span data-stu-id="3c880-152">Remarks</span></span>

<span data-ttu-id="3c880-153">追加のキーワードを指定せずに[End ステートメント](end-statement.md)を実行すると、すぐに実行が終了します。</span><span class="sxs-lookup"><span data-stu-id="3c880-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="3c880-154">スマートデバイスの開発者向けメモ</span><span class="sxs-lookup"><span data-stu-id="3c880-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="3c880-155">追加のキーワードを使用しない `End` ステートメントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3c880-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c880-156">参照</span><span class="sxs-lookup"><span data-stu-id="3c880-156">See also</span></span>

- [<span data-ttu-id="3c880-157">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="3c880-157">End Statement</span></span>](end-statement.md)
