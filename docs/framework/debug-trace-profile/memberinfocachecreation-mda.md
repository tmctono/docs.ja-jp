---
title: memberInfoCacheCreation MDA
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90f59f4d593a8aa077a6710cc0f5c1747ac1a3ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754001"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="4119b-102">memberInfoCacheCreation MDA</span><span class="sxs-lookup"><span data-stu-id="4119b-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="4119b-103">`memberInfoCacheCreation` マネージド デバッグ アシスタント (MDA) は、<xref:System.Reflection.MemberInfo> キャッシュが作成されるとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="4119b-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="4119b-104">これは、リソースに大きな負荷のかかるリフレクション機能をプログラムが使っていることを明確に示すものです。</span><span class="sxs-lookup"><span data-stu-id="4119b-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4119b-105">症状</span><span class="sxs-lookup"><span data-stu-id="4119b-105">Symptoms</span></span>  
 <span data-ttu-id="4119b-106">プログラムがリソースに負荷のかかるリフレクションを使っているため、プログラムのワーキング セットが増加します。</span><span class="sxs-lookup"><span data-stu-id="4119b-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4119b-107">原因</span><span class="sxs-lookup"><span data-stu-id="4119b-107">Cause</span></span>  
 <span data-ttu-id="4119b-108"><xref:System.Reflection.MemberInfo> オブジェクトが関係するリフレクション操作は、コールド ページに格納されているメタデータを読み取る必要があり、一般にプログラムが何らかの種類の遅延バインディング シナリオを使っていることを示すため、リソースに負荷がかかるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4119b-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4119b-109">解像度</span><span class="sxs-lookup"><span data-stu-id="4119b-109">Resolution</span></span>  
 <span data-ttu-id="4119b-110">この MDA を有効にした後にデバッガーでコードを実行するか、または MDA がアクティブになっているときにデバッガーとアタッチすることにより、プログラム内でリフレクションで使われている場所を特定できます。</span><span class="sxs-lookup"><span data-stu-id="4119b-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="4119b-111">デバッガーで実行すると、<xref:System.Reflection.MemberInfo> キャッシュが作成された場所を示すスタック トレースが取得され、その情報からプログラムがリフレクションを使っている場所を判断できます。</span><span class="sxs-lookup"><span data-stu-id="4119b-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="4119b-112">解決策は、コードの目的によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4119b-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="4119b-113">この MDA は、プログラムに遅延バインディング シナリオがあることを警告します。</span><span class="sxs-lookup"><span data-stu-id="4119b-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="4119b-114">事前バインディング シナリオに置き換えることができるかどうかを判断したり、遅延バインディング シナリオのパフォーマンスを検討したりできます。</span><span class="sxs-lookup"><span data-stu-id="4119b-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4119b-115">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="4119b-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="4119b-116">この MDA は、作成されるすべての <xref:System.Reflection.MemberInfo> キャッシュに対してアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="4119b-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="4119b-117">パフォーマンスに与える影響はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="4119b-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4119b-118">出力</span><span class="sxs-lookup"><span data-stu-id="4119b-118">Output</span></span>  
 <span data-ttu-id="4119b-119">MDA は、<xref:System.Reflection.MemberInfo> キャッシュが作成されたことを示すメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="4119b-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="4119b-120">プログラムがリフレクションを使っている場所を示すスタック トレースを取得するには、デバッガーを使います。</span><span class="sxs-lookup"><span data-stu-id="4119b-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4119b-121">構成</span><span class="sxs-lookup"><span data-stu-id="4119b-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="4119b-122">例</span><span class="sxs-lookup"><span data-stu-id="4119b-122">Example</span></span>  
 <span data-ttu-id="4119b-123">次のサンプル コードは、`memberInfoCacheCreation` MDA をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="4119b-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4119b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4119b-124">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="4119b-125">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="4119b-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
