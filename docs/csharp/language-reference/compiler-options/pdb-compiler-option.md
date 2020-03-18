---
title: -pdb (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 3081f4716e8cd858d789db6050e635af941aa05c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602566"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="8c5fe-102">-pdb (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="8c5fe-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="8c5fe-103">**-pdb** コンパイラ オプションは、デバッグ シンボル ファイルの場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c5fe-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="8c5fe-105">引数</span><span class="sxs-lookup"><span data-stu-id="8c5fe-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="8c5fe-106">デバッグ シンボル ファイルの名前と場所です。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c5fe-107">解説</span><span class="sxs-lookup"><span data-stu-id="8c5fe-107">Remarks</span></span>  
 <span data-ttu-id="8c5fe-108">[-debug (C# コンパイラ オプション)](./debug-compiler-option.md) を指定すると、コンパイラは、コンパイラが出力ファイル (.exe または .dll) を作成するのと同じディレクトリに、出力ファイルと同じ名前のファイル名で .pdb ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-108">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="8c5fe-109">**-pdb** では、.pdb ファイルに対し、既定以外のファイル名と場所を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="8c5fe-110">このコンパイラ オプションは、Visual Studio 開発環境で設定することはできません。また、プログラムで変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5fe-111">例</span><span class="sxs-lookup"><span data-stu-id="8c5fe-111">Example</span></span>  
 <span data-ttu-id="8c5fe-112">`t.cs` をコンパイルして、tt.pdb と呼ばれる .pdb ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c5fe-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c5fe-113">参照</span><span class="sxs-lookup"><span data-stu-id="8c5fe-113">See also</span></span>

- [<span data-ttu-id="8c5fe-114">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="8c5fe-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="8c5fe-115">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="8c5fe-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
