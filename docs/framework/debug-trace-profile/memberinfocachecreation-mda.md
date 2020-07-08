---
title: memberInfoCacheCreation MDA
description: .NET の memberInfoCacheCreation マネージデバッグアシスタント (MDA) について説明します。これは、MemberInfo キャッシュの作成時にアクティブ化されます。
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
ms.openlocfilehash: c48be7ac8632b8072981be01e01997ee8c34b6b3
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051143"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="e1062-103">memberInfoCacheCreation MDA</span><span class="sxs-lookup"><span data-stu-id="e1062-103">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="e1062-104">`memberInfoCacheCreation` マネージド デバッグ アシスタント (MDA) は、<xref:System.Reflection.MemberInfo> キャッシュが作成されるとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="e1062-104">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="e1062-105">これは、リソースに大きな負荷のかかるリフレクション機能をプログラムが使っていることを明確に示すものです。</span><span class="sxs-lookup"><span data-stu-id="e1062-105">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e1062-106">現象</span><span class="sxs-lookup"><span data-stu-id="e1062-106">Symptoms</span></span>  
 <span data-ttu-id="e1062-107">プログラムがリソースに負荷のかかるリフレクションを使っているため、プログラムのワーキング セットが増加します。</span><span class="sxs-lookup"><span data-stu-id="e1062-107">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e1062-108">原因</span><span class="sxs-lookup"><span data-stu-id="e1062-108">Cause</span></span>  
 <span data-ttu-id="e1062-109"><xref:System.Reflection.MemberInfo> オブジェクトが関係するリフレクション操作は、コールド ページに格納されているメタデータを読み取る必要があり、一般にプログラムが何らかの種類の遅延バインディング シナリオを使っていることを示すため、リソースに負荷がかかるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e1062-109">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e1062-110">解決方法</span><span class="sxs-lookup"><span data-stu-id="e1062-110">Resolution</span></span>  
 <span data-ttu-id="e1062-111">この MDA を有効にした後にデバッガーでコードを実行するか、または MDA がアクティブになっているときにデバッガーとアタッチすることにより、プログラム内でリフレクションで使われている場所を特定できます。</span><span class="sxs-lookup"><span data-stu-id="e1062-111">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="e1062-112">デバッガーで実行すると、<xref:System.Reflection.MemberInfo> キャッシュが作成された場所を示すスタック トレースが取得され、その情報からプログラムがリフレクションを使っている場所を判断できます。</span><span class="sxs-lookup"><span data-stu-id="e1062-112">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="e1062-113">解決策は、コードの目的によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1062-113">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="e1062-114">この MDA は、プログラムに遅延バインディング シナリオがあることを警告します。</span><span class="sxs-lookup"><span data-stu-id="e1062-114">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="e1062-115">事前バインディング シナリオに置き換えることができるかどうかを判断したり、遅延バインディング シナリオのパフォーマンスを検討したりできます。</span><span class="sxs-lookup"><span data-stu-id="e1062-115">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e1062-116">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="e1062-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="e1062-117">この MDA は、作成されるすべての <xref:System.Reflection.MemberInfo> キャッシュに対してアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e1062-117">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="e1062-118">パフォーマンスに与える影響はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="e1062-118">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e1062-119">出力</span><span class="sxs-lookup"><span data-stu-id="e1062-119">Output</span></span>  
 <span data-ttu-id="e1062-120">MDA は、<xref:System.Reflection.MemberInfo> キャッシュが作成されたことを示すメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="e1062-120">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="e1062-121">プログラムがリフレクションを使っている場所を示すスタック トレースを取得するには、デバッガーを使います。</span><span class="sxs-lookup"><span data-stu-id="e1062-121">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e1062-122">構成</span><span class="sxs-lookup"><span data-stu-id="e1062-122">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="e1062-123">例</span><span class="sxs-lookup"><span data-stu-id="e1062-123">Example</span></span>  
 <span data-ttu-id="e1062-124">次のサンプル コードは、`memberInfoCacheCreation` MDA をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="e1062-124">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1062-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1062-125">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="e1062-126">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="e1062-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
