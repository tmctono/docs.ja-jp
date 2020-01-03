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
ms.openlocfilehash: 8b57affa05c77d8ed20bfead7de767a8dd994241
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348592"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="9d923-102">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d923-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="9d923-103">コンパイラは、指定したアセンブリ内の型情報を、現在コンパイルしているプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d923-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d923-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d923-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="9d923-105">または</span><span class="sxs-lookup"><span data-stu-id="9d923-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d923-106">引数</span><span class="sxs-lookup"><span data-stu-id="9d923-106">Arguments</span></span>  
  
|<span data-ttu-id="9d923-107">用語</span><span class="sxs-lookup"><span data-stu-id="9d923-107">Term</span></span>|<span data-ttu-id="9d923-108">Definition</span><span class="sxs-lookup"><span data-stu-id="9d923-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="9d923-109">必須。</span><span class="sxs-lookup"><span data-stu-id="9d923-109">Required.</span></span> <span data-ttu-id="9d923-110">アセンブリ ファイル名のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="9d923-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="9d923-111">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9d923-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d923-112">コメント</span><span class="sxs-lookup"><span data-stu-id="9d923-112">Remarks</span></span>  
 <span data-ttu-id="9d923-113">インポートするファイルには、アセンブリメタデータが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d923-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="9d923-114">アセンブリの外部で参照できるのはパブリック型だけです。</span><span class="sxs-lookup"><span data-stu-id="9d923-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="9d923-115">[-Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)オプションは、モジュールからメタデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9d923-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="9d923-116">別のアセンブリ (アセンブリ B) を参照するアセンブリ (アセンブリ A) を参照する場合は、次の場合にアセンブリ B を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d923-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="9d923-117">アセンブリ A の型がアセンブリ B の型から継承されているか、アセンブリ B のインターフェイスを実装する。</span><span class="sxs-lookup"><span data-stu-id="9d923-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="9d923-118">アセンブリ B の戻り値の型またはパラメーターの型を使用するフィールド、プロパティ、イベント、またはメソッドが呼び出される。</span><span class="sxs-lookup"><span data-stu-id="9d923-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="9d923-119">アセンブリ参照が1つ以上存在するディレクトリを指定するには、 [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d923-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="9d923-120">コンパイラがアセンブリ (モジュールではない) の型を認識するには、型を強制的に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d923-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="9d923-121">これを行う方法の1つの例は、型のインスタンスを定義することです。</span><span class="sxs-lookup"><span data-stu-id="9d923-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="9d923-122">コンパイラのアセンブリの型名を解決するために、他の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d923-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="9d923-123">たとえば、アセンブリ内の型から継承する場合、型名はコンパイラに認識されます。</span><span class="sxs-lookup"><span data-stu-id="9d923-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="9d923-124">Vbc.exe ファイルは、一般的に使用される .NET Framework アセンブリを参照します。既定では、このファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d923-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="9d923-125">コンパイラで Vbc.exe を使用しない場合は、`-noconfig` を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d923-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="9d923-126">`-reference` の省略形は `/r` です。</span><span class="sxs-lookup"><span data-stu-id="9d923-126">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d923-127">例</span><span class="sxs-lookup"><span data-stu-id="9d923-127">Example</span></span>  
 <span data-ttu-id="9d923-128">次のコマンドは、`Metad1.dll` と `Metad2.dll` からソースファイル `Input.vb` と参照アセンブリをコンパイルして `Out.exe`を生成します。</span><span class="sxs-lookup"><span data-stu-id="9d923-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d923-129">参照</span><span class="sxs-lookup"><span data-stu-id="9d923-129">See also</span></span>

- [<span data-ttu-id="9d923-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="9d923-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9d923-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="9d923-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="9d923-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d923-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="9d923-133">Public</span><span class="sxs-lookup"><span data-stu-id="9d923-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="9d923-134">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="9d923-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
