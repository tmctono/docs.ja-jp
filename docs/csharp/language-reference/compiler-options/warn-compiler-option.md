---
description: -warn (C# コンパイラ オプション)
title: -warn (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 55e80d0bd05e2119154210503bb277d743050e18
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139074"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="85fe0-103">-warn (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="85fe0-103">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="85fe0-104">**-warn** オプションは、コンパイラが表示する警告レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-104">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85fe0-105">構文</span><span class="sxs-lookup"><span data-stu-id="85fe0-105">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="85fe0-106">引数</span><span class="sxs-lookup"><span data-stu-id="85fe0-106">Arguments</span></span>  
 `option`  
 <span data-ttu-id="85fe0-107">コンパイルで表示する警告レベル: 数値が小さいほど重要度が高い警告のみが表示され、数値が大きいほど多くの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="85fe0-107">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="85fe0-108">この値は、ゼロまたは正の整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="85fe0-108">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="85fe0-109">警告レベル</span><span class="sxs-lookup"><span data-stu-id="85fe0-109">Warning level</span></span>|<span data-ttu-id="85fe0-110">意味</span><span class="sxs-lookup"><span data-stu-id="85fe0-110">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="85fe0-111">0</span><span class="sxs-lookup"><span data-stu-id="85fe0-111">0</span></span>|<span data-ttu-id="85fe0-112">すべての警告メッセージの出力をオフにします。</span><span class="sxs-lookup"><span data-stu-id="85fe0-112">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="85fe0-113">1</span><span class="sxs-lookup"><span data-stu-id="85fe0-113">1</span></span>|<span data-ttu-id="85fe0-114">重大な警告メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-114">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="85fe0-115">2</span><span class="sxs-lookup"><span data-stu-id="85fe0-115">2</span></span>|<span data-ttu-id="85fe0-116">レベル 1 の警告に加え、クラス メンバーの非表示に関する警告など、より重大度の低い特定の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-116">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="85fe0-117">3</span><span class="sxs-lookup"><span data-stu-id="85fe0-117">3</span></span>|<span data-ttu-id="85fe0-118">レベル 2 の警告に加え、常に `true` または `false` に評価される式に関する警告など、より重大度の低い特定の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-118">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="85fe0-119">4 (既定)</span><span class="sxs-lookup"><span data-stu-id="85fe0-119">4 (the default)</span></span>|<span data-ttu-id="85fe0-120">レベルの 3 の警告に加え、情報のための警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-120">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="85fe0-121">5</span><span class="sxs-lookup"><span data-stu-id="85fe0-121">5</span></span>|<span data-ttu-id="85fe0-122">レベル 4 の警告に加え、C# 9.0 に含まれているコンパイラの[追加の警告](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md)を表示します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-122">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="85fe0-123">5 より大きい</span><span class="sxs-lookup"><span data-stu-id="85fe0-123">Greater than 5</span></span>|<span data-ttu-id="85fe0-124">5 より大きいすべての値は、5 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="85fe0-124">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="85fe0-125">コンパイラが新しい警告レベルで更新された場合に、必ずすべての警告が使用されるように、一般に任意の大きな値 (`9999` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-125">You generally put arbitrary large value (for example, `9999`) to make sure you always have all warnings if the compiler is updated with new warning levels.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="85fe0-126">注釈</span><span class="sxs-lookup"><span data-stu-id="85fe0-126">Remarks</span></span>  
 <span data-ttu-id="85fe0-127">エラーまたは警告に関する情報を取得するには、ヘルプの索引でエラー コードを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="85fe0-127">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="85fe0-128">エラーまたは警告に関する情報を取得する他の方法については、「[C# コンパイラ エラー](../compiler-messages/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fe0-128">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="85fe0-129">すべての警告をエラーとして扱う場合は [-warnaserror](./warnaserror-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-129">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="85fe0-130">特定の警告を無効にするには、[-nowarn](./nowarn-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-130">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="85fe0-131">**-w** は **-warn** の省略形です。</span><span class="sxs-lookup"><span data-stu-id="85fe0-131">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="85fe0-132">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="85fe0-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="85fe0-133">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="85fe0-133">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="85fe0-134">**[ビルド]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85fe0-134">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="85fe0-135">**警告レベル** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="85fe0-135">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="85fe0-136">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fe0-136">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85fe0-137">例</span><span class="sxs-lookup"><span data-stu-id="85fe0-137">Example</span></span>  
 <span data-ttu-id="85fe0-138">`in.cs` をコンパイルして、コンパイラにレベル 1 の警告のみを表示させます。</span><span class="sxs-lookup"><span data-stu-id="85fe0-138">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="85fe0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="85fe0-139">See also</span></span>

- [<span data-ttu-id="85fe0-140">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="85fe0-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="85fe0-141">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="85fe0-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
