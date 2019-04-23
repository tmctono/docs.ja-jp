---
title: -main (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 133aa22f16285f94f58722cb18c83b96f1ff885c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302791"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="1a33c-102">-main (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="1a33c-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="1a33c-103">このオプションは、**Main** メソッドを含むクラスが複数ある場合に、プログラムへのエントリ ポイントを含むクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a33c-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a33c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a33c-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="1a33c-105">引数</span><span class="sxs-lookup"><span data-stu-id="1a33c-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="1a33c-106">**Main** メソッドを含む型です。</span><span class="sxs-lookup"><span data-stu-id="1a33c-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="1a33c-107">指定するクラス名は完全に修飾する必要があります。クラスを含む完全な名前空間を指定し、そのあとにクラス名を続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a33c-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="1a33c-108">たとえば、`Main` メソッドが、`MyApplication.Core` 名前空間の `Program` クラス内に置かれている場合、コンパイラ オプションは `-main:MyApplication.Core.Program` とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a33c-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1a33c-109">解説</span><span class="sxs-lookup"><span data-stu-id="1a33c-109">Remarks</span></span>  
 <span data-ttu-id="1a33c-110">[Main](../../../csharp/programming-guide/main-and-command-args/index.md) メソッドを使用した型がコンパイル対象に 2 つ以上含まれている場合には、プログラムへのエントリ ポイントとして使用する **Main** メソッドがどの型に含まれているかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a33c-110">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="1a33c-111">このオプションは、.exe ファイルをコンパイルする際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a33c-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1a33c-112">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="1a33c-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="1a33c-113">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a33c-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="1a33c-114">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a33c-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="1a33c-115">**[スタートアップ オブジェクト]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="1a33c-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="1a33c-116">このコンパイラ オプションをプログラムによって設定するには、「<xref:VSLangProj80.ProjectProperties3.StartupObject%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a33c-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a33c-117">例</span><span class="sxs-lookup"><span data-stu-id="1a33c-117">Example</span></span>  
 <span data-ttu-id="1a33c-118">**Main** メソッドが`Test2` にあることを指定して、`t2.cs` と `t3.cs` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1a33c-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a33c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a33c-119">See also</span></span>

- [<span data-ttu-id="1a33c-120">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="1a33c-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="1a33c-121">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="1a33c-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
