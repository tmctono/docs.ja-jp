---
title: 'トラブルシューティング : ログ リスナー'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 8d2d8294d9e9bb42d72fe4f6c37bf846bd644907
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398319"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="041bb-102">トラブルシューティング: ログ リスナー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="041bb-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="041bb-103">`My.Application.Log` オブジェクトおよび `My.Log` オブジェクトを使用すると、アプリケーション内で発生したイベントに関する情報をログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="041bb-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="041bb-104">これらのメッセージをどのログ リスナーが受け取るかを確認するには、「[チュートリアル : My.Application.Log による情報の書き込み先の確認](walkthrough-determining-where-my-application-log-writes-information.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="041bb-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="041bb-105">`Log` オブジェクトでログ フィルターを使って、ログに記録される情報の量を制限できます。</span><span class="sxs-lookup"><span data-stu-id="041bb-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="041bb-106">フィルターが正しく構成されていない場合、ログに誤った情報が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="041bb-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="041bb-107">フィルターについて詳しくは、「[チュートリアル: My.Application.Log の出力をフィルター処理する](walkthrough-filtering-my-application-log-output.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="041bb-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="041bb-108">一方、ログが正しく構成されていない場合は、現在の構成についてさらに情報が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="041bb-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="041bb-109">ログの高度な `TraceSource` プロパティを使って、この情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="041bb-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="041bb-110">コードで Log オブジェクトのログ リスナーを特定するには</span><span class="sxs-lookup"><span data-stu-id="041bb-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="041bb-111">コード ファイルの先頭に <xref:System.Diagnostics> 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="041bb-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="041bb-112">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041bb-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="041bb-113">各ログ リスナーの情報で構成される文字列を返す関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="041bb-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="041bb-114">ログのトレース リスナーのコレクションを `GetListeners` 関数に渡し、戻り値を表示します。</span><span class="sxs-lookup"><span data-stu-id="041bb-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="041bb-115">詳細については、<xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041bb-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="041bb-116">参照</span><span class="sxs-lookup"><span data-stu-id="041bb-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="041bb-117">アプリケーション ログの使用</span><span class="sxs-lookup"><span data-stu-id="041bb-117">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="041bb-118">チュートリアル : My.Application.Log による情報の書き込み先の確認</span><span class="sxs-lookup"><span data-stu-id="041bb-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
