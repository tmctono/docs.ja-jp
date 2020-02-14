---
title: invalidGCHandleCookie MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: c1d8fab863c34313c0cdb778136c6f69a64defeb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216307"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="58566-102">invalidGCHandleCookie MDA</span><span class="sxs-lookup"><span data-stu-id="58566-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="58566-103">`invalidGCHandleCookie` マネージド デバッグ アシスタント (MDA) は、無効な <xref:System.IntPtr> Cookie から <xref:System.Runtime.InteropServices.GCHandle> への変換が試行されたときにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="58566-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="58566-104">現象</span><span class="sxs-lookup"><span data-stu-id="58566-104">Symptoms</span></span>  
 <span data-ttu-id="58566-105"><xref:System.Runtime.InteropServices.GCHandle> の使用または <xref:System.IntPtr> からの取得を試みているときのアクセス違反やメモリ破損などの定義されていない動作。</span><span class="sxs-lookup"><span data-stu-id="58566-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="58566-106">原因</span><span class="sxs-lookup"><span data-stu-id="58566-106">Cause</span></span>  
 <span data-ttu-id="58566-107">Cookie が <xref:System.Runtime.InteropServices.GCHandle> から最初に作成されていないために無効になっている可能性があります。既に解放されている <xref:System.Runtime.InteropServices.GCHandle> が異なるアプリケーション ドメイン内で <xref:System.Runtime.InteropServices.GCHandle> の Cookie になっているか、<xref:System.Runtime.InteropServices.GCHandle> としてネイティブ コードにマーシャリングされても、<xref:System.IntPtr> として CLR に再び渡され、キャストが試行されたことを表します。</span><span class="sxs-lookup"><span data-stu-id="58566-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="58566-108">解決策</span><span class="sxs-lookup"><span data-stu-id="58566-108">Resolution</span></span>  
 <span data-ttu-id="58566-109"><xref:System.IntPtr> の有効な <xref:System.Runtime.InteropServices.GCHandle> Cookie を指定します。</span><span class="sxs-lookup"><span data-stu-id="58566-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="58566-110">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="58566-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="58566-111">この MDA が有効になっているときには、返される Cookie の値が MDA が有効になっていないときに返される値と異なるので、デバッガはルートをオブジェクトまでトレースできなくなります。</span><span class="sxs-lookup"><span data-stu-id="58566-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="58566-112">出力</span><span class="sxs-lookup"><span data-stu-id="58566-112">Output</span></span>  
 <span data-ttu-id="58566-113">無効な <xref:System.IntPtr> Cookie 値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="58566-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="58566-114">構成</span><span class="sxs-lookup"><span data-stu-id="58566-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58566-115">参照</span><span class="sxs-lookup"><span data-stu-id="58566-115">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="58566-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="58566-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
