---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 35e02d1ad4409e754c2466f7d0ae7e68214772e6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716706"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="a7a40-102">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7a40-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="a7a40-103">コンパイラによって、指定されたアセンブリ内の型情報を、現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a40-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a40-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7a40-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="a7a40-105">or</span><span class="sxs-lookup"><span data-stu-id="a7a40-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a7a40-106">引数</span><span class="sxs-lookup"><span data-stu-id="a7a40-106">Arguments</span></span>  
  
|<span data-ttu-id="a7a40-107">用語</span><span class="sxs-lookup"><span data-stu-id="a7a40-107">Term</span></span>|<span data-ttu-id="a7a40-108">定義</span><span class="sxs-lookup"><span data-stu-id="a7a40-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="a7a40-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="a7a40-109">Required.</span></span> <span data-ttu-id="a7a40-110">アセンブリ ファイル名のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="a7a40-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="a7a40-111">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a7a40-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7a40-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7a40-112">Remarks</span></span>  
 <span data-ttu-id="a7a40-113">インポートするファイルには、アセンブリ メタデータが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a40-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="a7a40-114">アセンブリ外で表示されるのはパブリック型のみです。</span><span class="sxs-lookup"><span data-stu-id="a7a40-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="a7a40-115">[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) オプションでは、モジュールからメタデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a7a40-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="a7a40-116">あるアセンブリ (アセンブリ A) を参照していて、それ自体では別のアセンブリ (アセンブリ B) が参照される場合、次の場合はアセンブリ B を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a40-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="a7a40-117">アセンブリ A の型がアセンブリ B の型から継承されているか、アセンブリ B のインターフェイスを実装する。</span><span class="sxs-lookup"><span data-stu-id="a7a40-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="a7a40-118">アセンブリ B の戻り値の型またはパラメーターの型を使用するフィールド、プロパティ、イベント、またはメソッドが呼び出される。</span><span class="sxs-lookup"><span data-stu-id="a7a40-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="a7a40-119">1 つまたは複数のアセンブリ参照が配置されているディレクトリを指定するには、[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7a40-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="a7a40-120">コンパイラで (モジュールではなく) アセンブリの型を認識するには、型を強制的に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a40-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="a7a40-121">これを行う方法の 1 つの例は、型のインスタンスを定義することです。</span><span class="sxs-lookup"><span data-stu-id="a7a40-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="a7a40-122">コンパイラのアセンブリの型名を解決するために、他の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7a40-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="a7a40-123">たとえば、アセンブリの型から継承する場合、型名はコンパイラに認識されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7a40-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="a7a40-124">既定では、よく使われる .NET Framework アセンブリを参照する Vbc.rsp 応答ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7a40-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="a7a40-125">コンパイラで Vbc.rsp が使われないようにする場合は、`-noconfig` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7a40-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="a7a40-126">`-reference` の省略形は `-r` です。</span><span class="sxs-lookup"><span data-stu-id="a7a40-126">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7a40-127">例</span><span class="sxs-lookup"><span data-stu-id="a7a40-127">Example</span></span>  
 <span data-ttu-id="a7a40-128">次のコマンドでは、ソース ファイル `Input.vb` と、`Metad1.dll` および `Metad2.dll` からの参照アセンブリをコンパイルして、`Out.exe` を生成します。</span><span class="sxs-lookup"><span data-stu-id="a7a40-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7a40-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7a40-129">See also</span></span>

- [<span data-ttu-id="a7a40-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a7a40-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a7a40-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="a7a40-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="a7a40-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7a40-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="a7a40-133">Public</span><span class="sxs-lookup"><span data-stu-id="a7a40-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a7a40-134">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a7a40-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
