---
title: invalidMemberDeclaration MDA
description: InvalidMemberDeclaration マネージデバッグアシスタントを確認します。これは、マネージメソッドを呼び出さずに COM にエラー HRESULT が返された場合に呼び出されます。
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051715"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="e7422-103">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="e7422-103">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="e7422-104">`invalidMemberDeclaration` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、COM から呼び出されるメンバーのパラメーターをマーシャリングする方法を判断しているときに、エラーが発生したことを報告するためにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e7422-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e7422-105">現象</span><span class="sxs-lookup"><span data-stu-id="e7422-105">Symptoms</span></span>  
 <span data-ttu-id="e7422-106">マネージド メソッドが呼び出されることなく、COM にエラーの HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="e7422-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e7422-107">原因</span><span class="sxs-lookup"><span data-stu-id="e7422-107">Cause</span></span>  
 <span data-ttu-id="e7422-108">ほとんどの場合、いずれかのパラメーターに互換性のない <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性があることが原因です。</span><span class="sxs-lookup"><span data-stu-id="e7422-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e7422-109">解決方法</span><span class="sxs-lookup"><span data-stu-id="e7422-109">Resolution</span></span>  
 <span data-ttu-id="e7422-110">パラメーターで有効な <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7422-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e7422-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="e7422-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="e7422-112">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="e7422-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e7422-113">出力</span><span class="sxs-lookup"><span data-stu-id="e7422-113">Output</span></span>  
 <span data-ttu-id="e7422-114">メンバー名、型名、およびエラー メッセージを含む情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="e7422-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e7422-115">構成</span><span class="sxs-lookup"><span data-stu-id="e7422-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7422-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7422-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="e7422-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="e7422-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e7422-118">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="e7422-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
