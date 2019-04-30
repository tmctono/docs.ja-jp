---
title: パッケージ化とカスタム My 拡張 (Visual Basic) の配置
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014207"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="c605b-102">パッケージ化し、カスタム My 拡張 (Visual Basic) のデプロイ</span><span class="sxs-lookup"><span data-stu-id="c605b-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="c605b-103">Visual Basic では、ユーザー設定を展開するための簡単な方法`My`Visual Studio テンプレートを使用して名前空間の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="c605b-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="c605b-104">対象のプロジェクト テンプレートを作成する場合、`My`拡張機能は、新しいプロジェクトの種類の不可欠なカスタムを含めることができますのみ`My`テンプレートをエクスポートする場合は、プロジェクトで拡張機能のコード。</span><span class="sxs-lookup"><span data-stu-id="c605b-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="c605b-105">プロジェクト テンプレートをエクスポートする方法の詳細については、次を参照してください。[方法。プロジェクト テンプレートを作成](/visualstudio/ide/how-to-create-project-templates)です。</span><span class="sxs-lookup"><span data-stu-id="c605b-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="c605b-106">場合、カスタム`My`拡張機能が 1 つのコード ファイルに、ユーザーは、あらゆる種類の Visual Basic プロジェクトに追加できる項目テンプレートとして、ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c605b-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="c605b-107">追加の機能と、カスタムの動作を有効にする項目テンプレートをカスタマイズすることができますし`My`Visual Basic プロジェクトで拡張機能。</span><span class="sxs-lookup"><span data-stu-id="c605b-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="c605b-108">これらの機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c605b-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="c605b-109">ユーザーが、カスタム管理できるように`My`から拡張機能、**マイ拡張**Visual Basic のプロジェクト デザイナーのページ。</span><span class="sxs-lookup"><span data-stu-id="c605b-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="c605b-110">自動的に追加するカスタム`My`拡張機能と、指定したアセンブリへの参照がプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c605b-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="c605b-111">非表示、`My`拡張機能の項目テンプレートを**項目の追加**ダイアログ ボックスがプロジェクト項目の一覧には含まれません。</span><span class="sxs-lookup"><span data-stu-id="c605b-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="c605b-112">このトピックでは、カスタムのパッケージ化する方法を説明`My`拡張機能から管理可能な非表示の項目テンプレートとして、**マイ拡張**Visual Basic のプロジェクト デザイナーのページ。</span><span class="sxs-lookup"><span data-stu-id="c605b-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c605b-113">カスタム`My`拡張機能追加することも自動的に指定したアセンブリへの参照がプロジェクトに追加されたときにします。</span><span class="sxs-lookup"><span data-stu-id="c605b-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="c605b-114">作成、My 名前空間拡張</span><span class="sxs-lookup"><span data-stu-id="c605b-114">Create a My namespace extension</span></span>

<span data-ttu-id="c605b-115">カスタムの配置パッケージの作成の最初のステップ`My`拡張機能は、1 つのコード ファイルとして拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="c605b-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="c605b-116">詳細およびカスタムを作成する方法についてガイダンス`My`拡張機能を参照してください[Visual Basic の My Namespace の拡張](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)します。</span><span class="sxs-lookup"><span data-stu-id="c605b-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="c605b-117">エクスポートする項目のテンプレートと My 名前空間拡張</span><span class="sxs-lookup"><span data-stu-id="c605b-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="c605b-118">含むコード ファイルを作成したら、`My`名前空間の拡張機能は、Visual Studio 項目テンプレートとして、コード ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c605b-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="c605b-119">Visual Studio 項目テンプレートとしてファイルにエクスポートする方法の詳細については、次を参照してください。[方法。項目テンプレートを作成](/visualstudio/ide/how-to-create-item-templates)です。</span><span class="sxs-lookup"><span data-stu-id="c605b-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="c605b-120">場合、`My`名前空間の拡張機能は、特定のアセンブリに対する依存関係を持つ、自動的にインストールするように項目テンプレートをカスタマイズすることができます、`My`そのアセンブリへの参照が追加されたときに名前空間の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="c605b-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="c605b-121">その結果、コード ファイルを Visual Studio 項目テンプレートとしてエクスポートするときに、アセンブリ参照を除外するされます。</span><span class="sxs-lookup"><span data-stu-id="c605b-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="c605b-122">項目テンプレートをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c605b-122">Customize the item template</span></span>

<span data-ttu-id="c605b-123">項目テンプレートを管理することができます、**マイ拡張**Visual Basic のプロジェクト デザイナーのページ。</span><span class="sxs-lookup"><span data-stu-id="c605b-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c605b-124">項目テンプレートを指定したアセンブリへの参照がプロジェクトに追加されたときに自動的に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c605b-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="c605b-125">これらのカスタマイズを有効にするのには、テンプレート、CustomData ファイルと呼ばれる、新しいファイルに追加し、.vstemplate ファイルで XML を新しい要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="c605b-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="c605b-126">CustomData ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="c605b-126">Add the CustomData file</span></span>

<span data-ttu-id="c605b-127">CustomData ファイルは、ファイル名拡張子を持つテキスト ファイルです。CustomData (ファイル名設定できます任意の値に、テンプレートに意味のある) XML を格納しているとします。</span><span class="sxs-lookup"><span data-stu-id="c605b-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="c605b-128">CustomData ファイル内の XML を含める Visual Basic の指示、`My`ユーザーの使用時に拡張子、**マイ拡張**Visual Basic のプロジェクト デザイナーのページ。</span><span class="sxs-lookup"><span data-stu-id="c605b-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="c605b-129">必要に応じて追加することができます、<`AssemblyFullName>` CustomData ファイルの XML を属性します。</span><span class="sxs-lookup"><span data-stu-id="c605b-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="c605b-130">これにより、ユーザー設定を自動的にインストールする Visual Basic`My`特定のアセンブリへの参照時に拡張子がプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c605b-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="c605b-131">CustomData ファイルを作成する任意のテキスト エディターまたは XML エディターを使用し、項目テンプレートの圧縮フォルダー (.zip ファイル) に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c605b-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="c605b-132">たとえば、次の XML では Microsoft.VisualBasic.PowerPacks.Vs.dll アセンブリへの参照時に、Visual Basic プロジェクトの My の拡張機能フォルダーにテンプレート項目を追加する CustomData ファイルの内容は、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c605b-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="c605b-133">CustomData ファイルを含む、<`VBMyExtensionTemplate>`を次の表に記載されている属性を持つ要素。</span><span class="sxs-lookup"><span data-stu-id="c605b-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="c605b-134">属性</span><span class="sxs-lookup"><span data-stu-id="c605b-134">Attribute</span></span>|<span data-ttu-id="c605b-135">説明</span><span class="sxs-lookup"><span data-stu-id="c605b-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="c605b-136">必須。</span><span class="sxs-lookup"><span data-stu-id="c605b-136">Required.</span></span> <span data-ttu-id="c605b-137">拡張機能の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="c605b-137">A unique identifier for the extension.</span></span> <span data-ttu-id="c605b-138">この ID を持つ拡張機能は、プロジェクトに既に追加されている場合、もう一度追加するない、ユーザーが求められます。</span><span class="sxs-lookup"><span data-stu-id="c605b-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="c605b-139">必須。</span><span class="sxs-lookup"><span data-stu-id="c605b-139">Required.</span></span> <span data-ttu-id="c605b-140">項目テンプレートのバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="c605b-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="c605b-141">任意。</span><span class="sxs-lookup"><span data-stu-id="c605b-141">Optional.</span></span> <span data-ttu-id="c605b-142">アセンブリ名。</span><span class="sxs-lookup"><span data-stu-id="c605b-142">An assembly name.</span></span> <span data-ttu-id="c605b-143">追加するユーザーの入力を求め、このアセンブリへの参照がプロジェクトに追加されると、`My`この項目テンプレートからの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="c605b-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="c605b-144">追加、 \<CustomDataSignature > 要素を .vstemplate ファイル</span><span class="sxs-lookup"><span data-stu-id="c605b-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="c605b-145">として、Visual Studio 項目テンプレートを識別するために、`My`名前空間の拡張項目テンプレートの .vstemplate ファイルを変更することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="c605b-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="c605b-146">追加する必要があります、`<CustomDataSignature>`要素を`<TemplateData>`要素。</span><span class="sxs-lookup"><span data-stu-id="c605b-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="c605b-147">`<CustomDataSignature>`要素は、テキストを含める必要があります`Microsoft.VisualBasic.MyExtension`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="c605b-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="c605b-148">圧縮されたフォルダー (.zip ファイル) 内のファイルを直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c605b-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="c605b-149">.Vstemplate ファイルを圧縮フォルダーからコピー、変更、および、更新されたコピーを使用して、圧縮フォルダーの .vstemplate ファイルを置換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c605b-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="c605b-150">次の例を含む .vstemplate ファイルの内容を示しています、`<CustomDataSignature>`要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="c605b-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a><span data-ttu-id="c605b-151">テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c605b-151">Install the template</span></span>

<span data-ttu-id="c605b-152">テンプレートをインストールするには、圧縮フォルダーをコピーすることができます (*.zip*ファイル)、Visual Basic 項目テンプレート フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="c605b-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="c605b-153">既定では、ユーザー項目テンプレートに *%USERPROFILE%\Documents\Visual Studio\<バージョン\>\Templates\ItemTemplates\Visual Basic*します。</span><span class="sxs-lookup"><span data-stu-id="c605b-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="c605b-154">また、Visual Studio インストーラーとしてテンプレートを公開することができます (*.vsi*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="c605b-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="c605b-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="c605b-155">See also</span></span>

- [<span data-ttu-id="c605b-156">Visual Basic における My 名前空間の拡張</span><span class="sxs-lookup"><span data-stu-id="c605b-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="c605b-157">Visual Basic アプリケーション モデルの拡張</span><span class="sxs-lookup"><span data-stu-id="c605b-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="c605b-158">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c605b-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- <span data-ttu-id="c605b-159">[[マイ拡張] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="c605b-159">[My Extensions Page, Project Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>
