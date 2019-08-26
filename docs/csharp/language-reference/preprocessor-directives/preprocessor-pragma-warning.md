---
title: '#pragma warning - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: dc221235e78a187f921815ed6e6c7750778014d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922275"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="24150-102">#pragma warning (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="24150-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="24150-103">`#pragma warning` を使用すると、特定の警告を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24150-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24150-104">構文</span><span class="sxs-lookup"><span data-stu-id="24150-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="24150-105">parameters</span><span class="sxs-lookup"><span data-stu-id="24150-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="24150-106">警告番号のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="24150-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="24150-107">"CS" というプレフィックスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="24150-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="24150-108">警告番号が指定されていないと、`disable` はすべての警告を無効にし、`restore` はすべての警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24150-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24150-109">Visual Studio で警告番号を調べるには、プロジェクトをビルドし、 **[出力]** ウィンドウで警告番号を探してください。</span><span class="sxs-lookup"><span data-stu-id="24150-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24150-110">例</span><span class="sxs-lookup"><span data-stu-id="24150-110">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="24150-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="24150-111">See also</span></span>

- [<span data-ttu-id="24150-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="24150-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="24150-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="24150-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="24150-114">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="24150-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="24150-115">C# コンパイラ エラー</span><span class="sxs-lookup"><span data-stu-id="24150-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
