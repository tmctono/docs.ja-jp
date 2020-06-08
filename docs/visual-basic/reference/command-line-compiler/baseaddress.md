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
ms.openlocfilehash: d241584195da7d6f74b45b191c4f63204c200d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357181"
---
# <a name="-baseaddress"></a><span data-ttu-id="f4ffd-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="f4ffd-102">-baseaddress</span></span>
<span data-ttu-id="f4ffd-103">DLL を作成するときの既定のベース アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ffd-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4ffd-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4ffd-105">引数</span><span class="sxs-lookup"><span data-stu-id="f4ffd-105">Arguments</span></span>  
  
|<span data-ttu-id="f4ffd-106">用語</span><span class="sxs-lookup"><span data-stu-id="f4ffd-106">Term</span></span>|<span data-ttu-id="f4ffd-107">定義</span><span class="sxs-lookup"><span data-stu-id="f4ffd-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="f4ffd-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-108">Required.</span></span> <span data-ttu-id="f4ffd-109">DLL のベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-109">The base address for the DLL.</span></span> <span data-ttu-id="f4ffd-110">このアドレスは 16 進数として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4ffd-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4ffd-111">Remarks</span></span>  
 <span data-ttu-id="f4ffd-112">DLL の既定のベース アドレスは、.NET Framework により設定されます。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="f4ffd-113">このアドレスの下位ワードは丸められることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="f4ffd-114">たとえば、0x11110001 と指定すると、丸められて 0x11110000 になります。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="f4ffd-115">DLL の署名プロセスを完了するには、厳密名ツール (Sn.exe) の `–R` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="f4ffd-116">ターゲットが DLL でない場合、このオプションは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="f4ffd-117">Visual Studio IDE で -baseaddress を設定するには</span><span class="sxs-lookup"><span data-stu-id="f4ffd-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="f4ffd-118">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f4ffd-119">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f4ffd-120">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f4ffd-121">3. **[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="f4ffd-122">4. **[DLL ベース アドレス]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="f4ffd-123">**注:**    **[DLL ベース アドレス]** ボックスは、ターゲットが DLL の場合を除き、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="f4ffd-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4ffd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4ffd-124">See also</span></span>

- [<span data-ttu-id="f4ffd-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="f4ffd-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f4ffd-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4ffd-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="f4ffd-127">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="f4ffd-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="f4ffd-128">[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="f4ffd-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
