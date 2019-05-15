---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583378"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="bd7df-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd7df-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="bd7df-103">コンパイラが自動的に標準のライブラリを参照します。</span><span class="sxs-lookup"><span data-stu-id="bd7df-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7df-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd7df-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="bd7df-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd7df-105">Remarks</span></span>  
 <span data-ttu-id="bd7df-106">`-nostdlib`オプションは、System.dll アセンブリへの自動参照を削除し、コンパイラが Vbc.rsp ファイルを読み取ることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="bd7df-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="bd7df-107">Vbc.exe ファイルと同じディレクトリにある、Vbc.rsp ファイルは、一般的に使用される .NET Framework アセンブリを参照し、インポート、`System`と`Microsoft.VisualBasic`名前空間。</span><span class="sxs-lookup"><span data-stu-id="bd7df-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd7df-108">Mscorlib.dll および Microsoft.VisualBasic.dll のアセンブリは、常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="bd7df-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd7df-109">`-nostdlib`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="bd7df-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd7df-110">例</span><span class="sxs-lookup"><span data-stu-id="bd7df-110">Example</span></span>  
 <span data-ttu-id="bd7df-111">次のコードのコンパイル`T2.vb`標準ライブラリを参照することがなく。</span><span class="sxs-lookup"><span data-stu-id="bd7df-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="bd7df-112">設定する必要があります、`_MYTYPE`条件付きコンパイル定数文字列を削除するには、「空」に、`My`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bd7df-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd7df-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd7df-113">See also</span></span>

- [<span data-ttu-id="bd7df-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="bd7df-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="bd7df-115">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="bd7df-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bd7df-116">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="bd7df-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="bd7df-117">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bd7df-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
