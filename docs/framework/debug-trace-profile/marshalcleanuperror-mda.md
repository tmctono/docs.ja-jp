---
title: marshalCleanupError MDA
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab3690cac28ef572b19cadb632662590d1ea04c7
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052481"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="0f6cf-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="0f6cf-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="0f6cf-103">共通言語ランタイム (CLR) が、ネイティブ コードとマネージド コードの境界間でのデータ型のマーシャリングに使用した一時的な構造体とメモリをクリーンアップしようとしたときにエラーが発生すると、`marshalCleanupError` マネージド デバッグ アシスタント (MDA) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0f6cf-104">症状</span><span class="sxs-lookup"><span data-stu-id="0f6cf-104">Symptoms</span></span>  
 <span data-ttu-id="0f6cf-105">ネイティブ コードとマネージド コードの遷移を実行する場合、スレッド カルチャなどのランタイム状態が復元されない場合、または<xref:System.Runtime.InteropServices.SafeHandle> をクリーンアップしようしてエラーが発生した場合に、メモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0f6cf-106">原因</span><span class="sxs-lookup"><span data-stu-id="0f6cf-106">Cause</span></span>  
 <span data-ttu-id="0f6cf-107">一時的な構造体のクリーンアップ中に予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0f6cf-108">解決策</span><span class="sxs-lookup"><span data-stu-id="0f6cf-108">Resolution</span></span>  
 <span data-ttu-id="0f6cf-109">すべての <xref:System.Runtime.InteropServices.SafeHandle> デストラクター、ファイナライザー、カスタム マーシャラーの実装を調べ、エラーがないかどうかをレビューします。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0f6cf-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="0f6cf-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="0f6cf-111">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0f6cf-112">出力</span><span class="sxs-lookup"><span data-stu-id="0f6cf-112">Output</span></span>  
 <span data-ttu-id="0f6cf-113">クリーンアップ中に失敗した操作を報告するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0f6cf-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0f6cf-114">構成</span><span class="sxs-lookup"><span data-stu-id="0f6cf-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f6cf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f6cf-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="0f6cf-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="0f6cf-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0f6cf-117">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="0f6cf-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
