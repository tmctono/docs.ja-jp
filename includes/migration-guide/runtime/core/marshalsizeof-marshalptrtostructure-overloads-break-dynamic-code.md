---
ms.openlocfilehash: c462c7b4ec8423ce8fd331d3cd31154283cf1f1d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620260"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="1c8ae-101">Marshal.SizeOf および Marshal.PtrToStructure オーバー ロードがダイナミック コードを中断する</span><span class="sxs-lookup"><span data-stu-id="1c8ae-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="1c8ae-102">説明</span><span class="sxs-lookup"><span data-stu-id="1c8ae-102">Details</span></span>

<span data-ttu-id="1c8ae-103">.NET Framework 4.5.1 以降では、メソッド <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>、<xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>、または <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> への動的なバインドを (たとえば、Windows PowerShell、IronPython、または C# のダイナミック キーワードを使用して) 行うと、これらのメソッドの新しいオーバーロードが追加され、スクリプト エンジンにとってあいまいなことがあるため、<code>MethodInvocationExceptions</code> になります。</span><span class="sxs-lookup"><span data-stu-id="1c8ae-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c8ae-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1c8ae-104">Suggestion</span></span>

<span data-ttu-id="1c8ae-105">使用するオーバーロードを明確に示すように、スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="1c8ae-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="1c8ae-106">これは、一般に、メソッドの型パラメーターを <xref:System.Type> として明示的にキャストすることによって行われます。</span><span class="sxs-lookup"><span data-stu-id="1c8ae-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="1c8ae-107">この問題の回避方法の詳細と例については、[このリンク](https://support.microsoft.com/kb/2909958/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c8ae-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="1c8ae-108">名前</span><span class="sxs-lookup"><span data-stu-id="1c8ae-108">Name</span></span>    | <span data-ttu-id="1c8ae-109">[値]</span><span class="sxs-lookup"><span data-stu-id="1c8ae-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c8ae-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="1c8ae-110">Scope</span></span>   |<span data-ttu-id="1c8ae-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="1c8ae-111">Minor</span></span>|
|<span data-ttu-id="1c8ae-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="1c8ae-112">Version</span></span>|<span data-ttu-id="1c8ae-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="1c8ae-113">4.5.1</span></span>|
|<span data-ttu-id="1c8ae-114">種類</span><span class="sxs-lookup"><span data-stu-id="1c8ae-114">Type</span></span>|<span data-ttu-id="1c8ae-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1c8ae-115">Runtime</span></span>|
