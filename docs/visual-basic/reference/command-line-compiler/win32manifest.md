---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cae6b34aadf6698a337e52aa1ea1ce44206836ac
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004627"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="be4e9-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4e9-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="be4e9-103">プロジェクトのポータブル実行可能 (PE) ファイルに埋め込まれる、ユーザー定義の Win32 アプリケーション マニフェスト ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="be4e9-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="be4e9-105">引数</span><span class="sxs-lookup"><span data-stu-id="be4e9-105">Arguments</span></span>  
  
|<span data-ttu-id="be4e9-106">項目</span><span class="sxs-lookup"><span data-stu-id="be4e9-106">Term</span></span>|<span data-ttu-id="be4e9-107">定義</span><span class="sxs-lookup"><span data-stu-id="be4e9-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="be4e9-108">カスタムマニフェストファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="be4e9-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be4e9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="be4e9-109">Remarks</span></span>  
 <span data-ttu-id="be4e9-110">既定では、Visual Basic コンパイラは、asInvoker の要求実行レベルを指定するアプリケーションマニフェストを埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="be4e9-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="be4e9-111">実行可能ファイルがビルドされたフォルダー (通常は、Visual Studio を使用する場合は bin\Debug または bin\Release フォルダー) にマニフェストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="be4e9-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="be4e9-112">HighestAvailable または requireAdministrator の要求実行レベルを指定するなど、カスタムマニフェストを指定する場合は、このオプションを使用してファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be4e9-113">このオプションと[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="be4e9-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="be4e9-114">同じコマンドラインで両方のオプションを使用しようとすると、ビルドエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="be4e9-115">アプリケーション マニフェストを持たないアプリケーションは、要求実行レベルを指定した場合、Windows Vista のユーザー アカウント制御機能によって、ファイルまたはレジストリの仮想化の対象となります。</span><span class="sxs-lookup"><span data-stu-id="be4e9-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="be4e9-116">仮想化について詳しくは、「[Windows Vista の ClickOnce 配置](/visualstudio/deployment/clickonce-deployment-on-windows-vista)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be4e9-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="be4e9-117">次のいずれかの条件に該当する場合、アプリケーションは仮想化の対象になります。</span><span class="sxs-lookup"><span data-stu-id="be4e9-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="be4e9-118">@No__t-0 オプションを使用していて、後のビルド手順でマニフェストを提供していないか、または `-win32resource` オプションを使用して Windows リソース (.res) ファイルの一部として指定されていません。</span><span class="sxs-lookup"><span data-stu-id="be4e9-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="be4e9-119">要求実行レベルが指定されていないカスタム マニフェストを提供している。</span><span class="sxs-lookup"><span data-stu-id="be4e9-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="be4e9-120">Visual Studio は、既定の .manifest ファイルを作成し、それを実行可能ファイルと一緒にデバッグ ディレクトリとリリース ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="be4e9-121">既定のアプリケーションマニフェストファイルを表示または編集するには、プロジェクトデザイナーの **[アプリケーション]** タブで **[UAC 設定の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be4e9-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="be4e9-122">詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be4e9-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="be4e9-123">アプリケーションマニフェストは、カスタムのビルド後の手順として提供することも、`-nowin32manifest` オプションを使用して Win32 リソースファイルの一部として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="be4e9-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="be4e9-124">アプリケーションを Windows Vista でファイルまたはレジストリの仮想化の対象にする場合は、これと同じオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="be4e9-125">これにより、コンパイラは既定のマニフェストを作成し、PE ファイルに埋め込むことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="be4e9-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be4e9-126">例</span><span class="sxs-lookup"><span data-stu-id="be4e9-126">Example</span></span>  
 <span data-ttu-id="be4e9-127">次の例は、Visual Basic コンパイラによって PE に挿入される既定のマニフェストを示しています。</span><span class="sxs-lookup"><span data-stu-id="be4e9-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be4e9-128">コンパイラは、標準のアプリケーション名 MyApplication をマニフェスト XML に挿入します。</span><span class="sxs-lookup"><span data-stu-id="be4e9-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="be4e9-129">これは、アプリケーションを Windows Server 2003 Service Pack 3 で実行できるようにするための回避策です。</span><span class="sxs-lookup"><span data-stu-id="be4e9-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be4e9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="be4e9-130">See also</span></span>

- [<span data-ttu-id="be4e9-131">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="be4e9-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="be4e9-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4e9-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
