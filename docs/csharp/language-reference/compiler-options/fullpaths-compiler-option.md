---
description: -fullpaths (C# コンパイラ オプション)
title: -fullpaths (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
ms.openlocfilehash: 1ea1c3ec5e0d981c36044351d02d459386a720fc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173218"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="b464c-103">-fullpaths (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="b464c-103">-fullpaths (C# Compiler Options)</span></span>

<span data-ttu-id="b464c-104">**-fullpaths** オプションを指定すると、コンパイルのエラーや警告を一覧表示するとき、コンパイラはファイルの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b464c-104">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b464c-105">構文</span><span class="sxs-lookup"><span data-stu-id="b464c-105">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="b464c-106">解説</span><span class="sxs-lookup"><span data-stu-id="b464c-106">Remarks</span></span>  

 <span data-ttu-id="b464c-107">既定では、コンパイルの結果として発生したエラーや警告には、エラーが見つかったファイルの名前が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b464c-107">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="b464c-108">**-fullpaths** オプションを指定すると、コンパイラはファイルの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b464c-108">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="b464c-109">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b464c-109">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b464c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b464c-110">See also</span></span>

- [<span data-ttu-id="b464c-111">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="b464c-111">C# Compiler Options</span></span>](./index.md)
