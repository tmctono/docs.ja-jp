---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964357"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="70152-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70152-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="70152-103">コンパイラが標準ライブラリを自動的に参照しないようにします。</span><span class="sxs-lookup"><span data-stu-id="70152-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70152-104">構文</span><span class="sxs-lookup"><span data-stu-id="70152-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="70152-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="70152-105">Remarks</span></span>  
 <span data-ttu-id="70152-106">`-nostdlib`オプションを指定すると、System .dll アセンブリへの自動参照が削除され、コンパイラが vbc.exe ファイルを読み取ることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="70152-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="70152-107">Vbc.exe ファイルと同じディレクトリにある vbc.exe ファイルは、一般的に使用される .NET Framework アセンブリを参照し、名前空間`System`と`Microsoft.VisualBasic`名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="70152-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70152-108">Mscorlib.dll および Microsoft の .dll アセンブリは常に参照されます。</span><span class="sxs-lookup"><span data-stu-id="70152-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70152-109">この`-nostdlib`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="70152-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70152-110">例</span><span class="sxs-lookup"><span data-stu-id="70152-110">Example</span></span>  
 <span data-ttu-id="70152-111">次のコードは`T2.vb` 、標準ライブラリを参照せずにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="70152-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="70152-112">オブジェクト`My`を削除する`_MYTYPE`には、条件付きコンパイル定数を文字列 "Empty" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70152-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="70152-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="70152-113">See also</span></span>

- [<span data-ttu-id="70152-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="70152-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="70152-115">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="70152-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="70152-116">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="70152-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="70152-117">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="70152-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
