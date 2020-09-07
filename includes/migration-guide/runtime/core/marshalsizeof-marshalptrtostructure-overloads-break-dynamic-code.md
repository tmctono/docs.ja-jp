---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497020"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="d7ff8-101">Marshal.SizeOf および Marshal.PtrToStructure オーバー ロードがダイナミック コードを中断する</span><span class="sxs-lookup"><span data-stu-id="d7ff8-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="d7ff8-102">説明</span><span class="sxs-lookup"><span data-stu-id="d7ff8-102">Details</span></span>

<span data-ttu-id="d7ff8-103">.NET Framework 4.5.1 以降では、メソッド <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>、<xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>、または <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> への動的なバインドを (たとえば、Windows PowerShell、IronPython、または C# のダイナミック キーワードを使用して) 行うと、これらのメソッドの新しいオーバーロードが追加され、スクリプト エンジンにとってあいまいなことがあるため、<code>MethodInvocationExceptions</code> になります。</span><span class="sxs-lookup"><span data-stu-id="d7ff8-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7ff8-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d7ff8-104">Suggestion</span></span>

<span data-ttu-id="d7ff8-105">使用するオーバーロードを明確に示すように、スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="d7ff8-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="d7ff8-106">これは、一般に、メソッドの型パラメーターを <xref:System.Type> として明示的にキャストすることによって行われます。</span><span class="sxs-lookup"><span data-stu-id="d7ff8-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="d7ff8-107">この問題の回避方法の詳細と例については、[このリンク](https://support.microsoft.com/kb/2909958/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7ff8-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="d7ff8-108">名前</span><span class="sxs-lookup"><span data-stu-id="d7ff8-108">Name</span></span>    | <span data-ttu-id="d7ff8-109">[値]</span><span class="sxs-lookup"><span data-stu-id="d7ff8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7ff8-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="d7ff8-110">Scope</span></span>   |<span data-ttu-id="d7ff8-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="d7ff8-111">Minor</span></span>|
|<span data-ttu-id="d7ff8-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="d7ff8-112">Version</span></span>|<span data-ttu-id="d7ff8-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d7ff8-113">4.5.1</span></span>|
|<span data-ttu-id="d7ff8-114">種類</span><span class="sxs-lookup"><span data-stu-id="d7ff8-114">Type</span></span>|<span data-ttu-id="d7ff8-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d7ff8-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d7ff8-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d7ff8-116">Affected APIs</span></span>

<span data-ttu-id="d7ff8-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="d7ff8-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
