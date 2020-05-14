---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002390"
---
# <a name="-baseaddress"></a><span data-ttu-id="0929a-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="0929a-102">-baseaddress</span></span>
<span data-ttu-id="0929a-103">DLL を作成するときの既定のベース アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0929a-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0929a-104">構文</span><span class="sxs-lookup"><span data-stu-id="0929a-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="0929a-105">引数</span><span class="sxs-lookup"><span data-stu-id="0929a-105">Arguments</span></span>  
  
|<span data-ttu-id="0929a-106">用語</span><span class="sxs-lookup"><span data-stu-id="0929a-106">Term</span></span>|<span data-ttu-id="0929a-107">定義</span><span class="sxs-lookup"><span data-stu-id="0929a-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="0929a-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="0929a-108">Required.</span></span> <span data-ttu-id="0929a-109">DLL のベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="0929a-109">The base address for the DLL.</span></span> <span data-ttu-id="0929a-110">このアドレスは 16 進数として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0929a-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0929a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0929a-111">Remarks</span></span>  
 <span data-ttu-id="0929a-112">DLL の既定のベース アドレスは、.NET Framework により設定されます。</span><span class="sxs-lookup"><span data-stu-id="0929a-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="0929a-113">このアドレスの下位ワードは丸められることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="0929a-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="0929a-114">たとえば、0x11110001 と指定すると、丸められて 0x11110000 になります。</span><span class="sxs-lookup"><span data-stu-id="0929a-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="0929a-115">DLL の署名プロセスを完了するには、厳密名ツール (Sn.exe) の `–R` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0929a-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="0929a-116">ターゲットが DLL でない場合、このオプションは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0929a-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="0929a-117">Visual Studio IDE で -baseaddress を設定するには</span><span class="sxs-lookup"><span data-stu-id="0929a-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0929a-118">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0929a-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0929a-119">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0929a-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0929a-120">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0929a-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0929a-121">3. **[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0929a-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="0929a-122">4. **[DLL ベース アドレス]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0929a-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="0929a-123">**注:**    **[DLL ベース アドレス]** ボックスは、ターゲットが DLL の場合を除き、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="0929a-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0929a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0929a-124">See also</span></span>

- [<span data-ttu-id="0929a-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="0929a-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0929a-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0929a-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="0929a-127">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="0929a-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="0929a-128">[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="0929a-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
