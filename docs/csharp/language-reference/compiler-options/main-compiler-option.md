---
description: -main (C# コンパイラ オプション)
title: -main (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194116"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="a4c93-103">-main (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="a4c93-103">-main (C# Compiler Options)</span></span>

<span data-ttu-id="a4c93-104">このオプションは、**Main** メソッドを含むクラスが複数ある場合に、プログラムへのエントリ ポイントを含むクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4c93-104">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4c93-105">構文</span><span class="sxs-lookup"><span data-stu-id="a4c93-105">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="a4c93-106">引数</span><span class="sxs-lookup"><span data-stu-id="a4c93-106">Arguments</span></span>

 `class`  
 <span data-ttu-id="a4c93-107">**Main** メソッドを含む型です。</span><span class="sxs-lookup"><span data-stu-id="a4c93-107">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="a4c93-108">指定するクラス名は完全に修飾する必要があります。クラスを含む完全な名前空間を指定し、そのあとにクラス名を続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4c93-108">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="a4c93-109">たとえば、`Main` メソッドが、`MyApplication.Core` 名前空間の `Program` クラス内に置かれている場合、コンパイラ オプションは `-main:MyApplication.Core.Program` とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4c93-109">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4c93-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4c93-110">Remarks</span></span>

<span data-ttu-id="a4c93-111">[Main](../../programming-guide/main-and-command-args/index.md) メソッドを使用した型がコンパイル対象に 2 つ以上含まれている場合には、プログラムへのエントリ ポイントとして使用する **Main** メソッドがどの型に含まれているかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4c93-111">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="a4c93-112">このオプションは、 *.exe* ファイルをコンパイルするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4c93-112">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a4c93-113">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="a4c93-113">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="a4c93-114">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="a4c93-114">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="a4c93-115">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4c93-115">Click the **Application** property page.</span></span>

3. <span data-ttu-id="a4c93-116">**[スタートアップ オブジェクト]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a4c93-116">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="a4c93-117">このコンパイラ オプションをプログラムによって設定するには、「<xref:VSLangProj80.ProjectProperties3.StartupObject%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4c93-117">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="a4c93-118">*.csproj* ファイルを手動で編集してこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="a4c93-118">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="a4c93-119">.csproj ファイルを編集し、`PropertyGroup` セクション内に `StartupObject` 要素を追加することで、このオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4c93-119">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="a4c93-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a4c93-120">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="a4c93-121">例</span><span class="sxs-lookup"><span data-stu-id="a4c93-121">Example</span></span>

<span data-ttu-id="a4c93-122">**Main** メソッドが`Test2` にあることを指定して、`t2.cs` と `t3.cs` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a4c93-122">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="a4c93-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4c93-123">See also</span></span>

- [<span data-ttu-id="a4c93-124">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="a4c93-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a4c93-125">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="a4c93-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
