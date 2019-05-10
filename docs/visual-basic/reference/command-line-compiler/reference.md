---
title: -参照 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: a205682bb15b5d25ba0a2df895533d3443a41409
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663465"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="46cfb-102">-参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46cfb-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="46cfb-103">コンパイラで型情報をコンパイルする現在のプロジェクトで使用できる、指定されたアセンブリでようにします。</span><span class="sxs-lookup"><span data-stu-id="46cfb-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46cfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="46cfb-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="46cfb-105">引数</span><span class="sxs-lookup"><span data-stu-id="46cfb-105">Arguments</span></span>  
  
|<span data-ttu-id="46cfb-106">用語</span><span class="sxs-lookup"><span data-stu-id="46cfb-106">Term</span></span>|<span data-ttu-id="46cfb-107">定義</span><span class="sxs-lookup"><span data-stu-id="46cfb-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="46cfb-108">必須。</span><span class="sxs-lookup"><span data-stu-id="46cfb-108">Required.</span></span> <span data-ttu-id="46cfb-109">アセンブリ ファイル名のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="46cfb-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="46cfb-110">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="46cfb-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46cfb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="46cfb-111">Remarks</span></span>  
 <span data-ttu-id="46cfb-112">ファイルをインポートするには、アセンブリ メタデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="46cfb-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="46cfb-113">パブリック型だけでは、アセンブリの外側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="46cfb-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="46cfb-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)オプションは、モジュールからメタデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="46cfb-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="46cfb-115">アセンブリ (アセンブリ A) を参照する場合は、別のアセンブリ (アセンブリ B) を参照する、場合、アセンブリ B を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46cfb-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="46cfb-116">アセンブリ A の型がアセンブリ B の型から継承されているか、アセンブリ B のインターフェイスを実装する。</span><span class="sxs-lookup"><span data-stu-id="46cfb-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="46cfb-117">アセンブリ B の戻り値の型またはパラメーターの型を使用するフィールド、プロパティ、イベント、またはメソッドが呼び出される。</span><span class="sxs-lookup"><span data-stu-id="46cfb-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="46cfb-118">使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)を 1 つ以上のアセンブリ参照があるディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="46cfb-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="46cfb-119">コンパイラがアセンブリ (モジュールではなく) 内の型を認識するには、型の解決を強制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46cfb-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="46cfb-120">これを実行する方法の 1 つの例では、型のインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="46cfb-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="46cfb-121">その他の方法、コンパイラのアセンブリ内の型名を解決するのには利用できます。</span><span class="sxs-lookup"><span data-stu-id="46cfb-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="46cfb-122">たとえば、アセンブリ内の型から継承する場合、型名し既知となるコンパイラに。</span><span class="sxs-lookup"><span data-stu-id="46cfb-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="46cfb-123">参照がよく使用される、Vbc.rsp 応答ファイル[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]アセンブリでは、既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="46cfb-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="46cfb-124">使用して、`-noconfig`コンパイラが Vbc.rsp を使用したくない場合。</span><span class="sxs-lookup"><span data-stu-id="46cfb-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="46cfb-125">`-reference` の省略形は `/r` です。</span><span class="sxs-lookup"><span data-stu-id="46cfb-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46cfb-126">例</span><span class="sxs-lookup"><span data-stu-id="46cfb-126">Example</span></span>  
 <span data-ttu-id="46cfb-127">次のコマンドは、ソース ファイルをコンパイル`Input.vb`からの参照アセンブリと`Metad1.dll`と`Metad2.dll`を生成する`Out.exe`します。</span><span class="sxs-lookup"><span data-stu-id="46cfb-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="46cfb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="46cfb-128">See also</span></span>

- [<span data-ttu-id="46cfb-129">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="46cfb-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="46cfb-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="46cfb-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="46cfb-131">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46cfb-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="46cfb-132">Public</span><span class="sxs-lookup"><span data-stu-id="46cfb-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="46cfb-133">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="46cfb-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
