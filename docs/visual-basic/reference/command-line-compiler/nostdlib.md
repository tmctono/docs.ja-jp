---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 0934799853323110e73087ba6d8975c30f84d8f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387713"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="ce755-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce755-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="ce755-103">コンパイラが標準ライブラリを自動的に参照しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ce755-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce755-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce755-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="ce755-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce755-105">Remarks</span></span>  
 <span data-ttu-id="ce755-106">`-nostdlib` オプションを指定すると、System.dll アセンブリへの自動参照が削除され、コンパイラで Vbc.rsp ファイルを読み取れないようにします。</span><span class="sxs-lookup"><span data-stu-id="ce755-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="ce755-107">Vbc.rsp ファイルは、Vbc.exe ファイルと同じディレクトリにあり、一般的に使用される .NET Framework アセンブリを参照し、`System` と `Microsoft.VisualBasic` の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ce755-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce755-108">Mscorlib.dll アセンブリおよび Microsoft.VisualBasic.dll アセンブリは常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="ce755-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce755-109">`-nostdlib` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce755-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce755-110">例</span><span class="sxs-lookup"><span data-stu-id="ce755-110">Example</span></span>  
 <span data-ttu-id="ce755-111">次のコードでは、標準ライブラリを参照されずに `T2.vb` がコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="ce755-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="ce755-112">`My` オブジェクトを削除するには、`_MYTYPE` 条件付きコンパイル定数を文字列 "Empty" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce755-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce755-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce755-113">See also</span></span>

- [<span data-ttu-id="ce755-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ce755-114">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="ce755-115">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ce755-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ce755-116">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="ce755-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="ce755-117">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ce755-117">Customizing Which Objects are Available in My</span></span>](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
