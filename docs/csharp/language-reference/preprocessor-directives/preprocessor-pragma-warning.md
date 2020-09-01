---
description: '#pragma warning - C# リファレンス'
title: '#pragma warning - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3085c21db386ca215d48bbe8ade83cd26732242c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137969"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="2037b-103">#pragma 警告 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2037b-103">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="2037b-104">`#pragma warning` を使用すると、特定の警告を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2037b-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2037b-105">構文</span><span class="sxs-lookup"><span data-stu-id="2037b-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="2037b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2037b-106">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="2037b-107">警告番号のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="2037b-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="2037b-108">"CS" というプレフィックスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2037b-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="2037b-109">警告番号が指定されていないと、`disable` はすべての警告を無効にし、`restore` はすべての警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2037b-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2037b-110">Visual Studio で警告番号を調べるには、プロジェクトをビルドし、**[出力]** ウィンドウで警告番号を探してください。</span><span class="sxs-lookup"><span data-stu-id="2037b-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2037b-111">例</span><span class="sxs-lookup"><span data-stu-id="2037b-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2037b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2037b-112">See also</span></span>

- [<span data-ttu-id="2037b-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2037b-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2037b-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2037b-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2037b-115">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2037b-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="2037b-116">C# コンパイラ エラー</span><span class="sxs-lookup"><span data-stu-id="2037b-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
