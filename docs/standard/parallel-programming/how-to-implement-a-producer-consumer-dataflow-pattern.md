---
title: '方法: プロデューサー/コンシューマーのデータフロー パターンを実装する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 044e726a1c668335780fe3d4322fbce83d8dcbba
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666358"
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="d03ec-102">方法: プロデューサー/コンシューマーのデータフロー パターンを実装する</span><span class="sxs-lookup"><span data-stu-id="d03ec-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="d03ec-103">このドキュメントでは、TPL データフロー ライブラリを使用して、プロデューサー/コンシューマー パターンを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="d03ec-104">このパターンでは、"*プロデューサー*" がメッセージをメッセージ ブロックに送信し、"*コンシューマー*" がそのブロックからメッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d03ec-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a><span data-ttu-id="d03ec-105">例</span><span class="sxs-lookup"><span data-stu-id="d03ec-105">Example</span></span>  
 <span data-ttu-id="d03ec-106">次の例では、データフローを使用する基本的なプロデューサー/コンシューマー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-106">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="d03ec-107">`Produce` メソッドは、データのランダム バイトを含む配列を <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> オブジェクトに書き込み、`Consume` メソッドは <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> オブジェクトからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d03ec-107">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="d03ec-108">派生型ではなく、<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> と <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> のインターフェイス上で動作することで、さまざまなデータフロー ブロック型上で動作する再利用可能なコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="d03ec-108">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="d03ec-109">この例では、<xref:System.Threading.Tasks.Dataflow.BufferBlock%601> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-109">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="d03ec-110"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> クラスはソース ブロックとターゲット ブロックの両方として機能するため、プロデューサーおよびコンシューマーは共有されたオブジェクトを使用してデータを転送できます。</span><span class="sxs-lookup"><span data-stu-id="d03ec-110">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="d03ec-111">`Produce` メソッドはループ内で <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> メソッドを呼び出し、ターゲット ブロックにデータを同期的に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d03ec-111">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="d03ec-112">`Produce` メソッドはターゲット ブロックにすべてのデータを書き込んだ後、<xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> メソッドを呼び出して、このブロックに使用可能なデータが追加されないように指示します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-112">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="d03ec-113">`Consume` メソッドでは、[async](../../csharp/language-reference/keywords/async.md) 演算子と [await](../../csharp/language-reference/keywords/await.md) 演算子 (Visual Basic では [Async](../../visual-basic/language-reference/modifiers/async.md) と [Await](../../visual-basic/language-reference/operators/await-operator.md)) を使用して、<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> オブジェクトから受信した合計バイト数を非同期的に計算します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-113">The `Consume` method uses the [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/keywords/await.md) operators ([Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="d03ec-114">非同期的に動作するために、`Consume` メソッドは <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> メソッドを呼び出して、ソース ブロックに使用可能なデータがあるときとソース ブロックに使用可能なデータが追加されなくなったときに、通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-114">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d03ec-115">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="d03ec-115">Robust Programming</span></span>  
 <span data-ttu-id="d03ec-116">上記の例では、1 つのコンシューマーのみを使用してソース データを処理します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-116">The preceding example uses just one consumer to process the source data.</span></span> <span data-ttu-id="d03ec-117">アプリケーションに複数のコンシューマーがある場合は、次の例に示すように、<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> メソッドを使用してソース ブロックからデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d03ec-117">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="d03ec-118"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> メソッドは、データを使用できないときに `False` を返します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-118">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="d03ec-119">複数のコンシューマーがソース ブロックに同時にアクセスする必要がある場合、この仕組みが、<xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> の呼び出し後もデータを使用可能なことを保証します。</span><span class="sxs-lookup"><span data-stu-id="d03ec-119">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03ec-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d03ec-120">See also</span></span>

- [<span data-ttu-id="d03ec-121">データフロー</span><span class="sxs-lookup"><span data-stu-id="d03ec-121">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
