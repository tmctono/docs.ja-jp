---
title: カスタム My 拡張のパッケージ化と配置
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330257"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="26c60-102">カスタムマイ拡張のパッケージ化と配置 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26c60-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="26c60-103">Visual Basic では、Visual Studio テンプレートを使用してカスタム `My` 名前空間拡張を簡単にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="26c60-104">`My` の拡張機能が新しいプロジェクトの種類の不可欠な部分であるプロジェクトテンプレートを作成する場合は、テンプレートをエクスポートするときに、カスタムの `My` 拡張機能コードをプロジェクトに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="26c60-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="26c60-105">プロジェクトテンプレートのエクスポートの詳細については、「[方法: プロジェクトテンプレートを作成する](/visualstudio/ide/how-to-create-project-templates)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c60-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="26c60-106">カスタム `My` 拡張機能が1つのコードファイル内にある場合は、ユーザーが任意の種類の Visual Basic プロジェクトに追加できる項目テンプレートとして、ファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="26c60-107">次に、項目テンプレートをカスタマイズして、Visual Basic プロジェクトのカスタム `My` 拡張機能の追加機能と動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="26c60-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="26c60-108">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="26c60-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="26c60-109">ユーザーが Visual Basic プロジェクトデザイナーの **[マイ拡張**] ページからカスタム `My` 拡張機能を管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="26c60-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="26c60-110">指定したアセンブリへの参照がプロジェクトに追加されたときに、カスタム `My` 拡張機能を自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="26c60-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="26c60-111">**[項目の追加]** ダイアログボックスで `My` 拡張項目テンプレートを非表示にして、プロジェクト項目の一覧に含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="26c60-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="26c60-112">このトピックでは、Visual Basic プロジェクトデザイナーの **[マイ拡張**] ページから管理できる非表示項目テンプレートとして、カスタム `My` 拡張機能をパッケージ化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26c60-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="26c60-113">また、指定したアセンブリへの参照がプロジェクトに追加されたときに、カスタム `My` 拡張機能を自動的に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="26c60-114">マイ名前空間拡張を作成する</span><span class="sxs-lookup"><span data-stu-id="26c60-114">Create a My namespace extension</span></span>

<span data-ttu-id="26c60-115">カスタム `My` 拡張機能の配置パッケージを作成する最初の手順は、拡張機能を1つのコードファイルとして作成することです。</span><span class="sxs-lookup"><span data-stu-id="26c60-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="26c60-116">カスタム `My` 拡張機能を作成する方法の詳細とガイダンスについては、「 [Visual Basic での My 名前空間の拡張](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c60-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="26c60-117">マイ名前空間拡張を項目テンプレートとしてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="26c60-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="26c60-118">`My` 名前空間拡張機能を含むコードファイルを作成した後は、Visual Studio 項目テンプレートとしてコードファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="26c60-119">ファイルを Visual Studio 項目テンプレートとしてエクスポートする方法については、「[方法: 項目テンプレートを作成](/visualstudio/ide/how-to-create-item-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c60-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="26c60-120">`My` 名前空間拡張が特定のアセンブリに依存している場合は、そのアセンブリへの参照が追加されるときに、`My` 名前空間拡張機能を自動的にインストールするように項目テンプレートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="26c60-121">そのため、Visual Studio 項目テンプレートとしてコードファイルをエクスポートするときに、そのアセンブリ参照を除外することができます。</span><span class="sxs-lookup"><span data-stu-id="26c60-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="26c60-122">項目テンプレートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="26c60-122">Customize the item template</span></span>

<span data-ttu-id="26c60-123">項目テンプレートは、Visual Basic プロジェクトデザイナーの **[マイ拡張**] ページから管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="26c60-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="26c60-124">指定したアセンブリへの参照がプロジェクトに追加されたときに、項目テンプレートが自動的に追加されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="26c60-125">これらのカスタマイズを有効にするには、CustomData ファイルという名前の新しいファイルをテンプレートに追加し、.vstemplate ファイルの XML に新しい要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="26c60-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="26c60-126">CustomData ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="26c60-126">Add the CustomData file</span></span>

<span data-ttu-id="26c60-127">CustomData ファイルは、というファイル名拡張子を持つテキストファイルです。CustomData (ファイル名は、テンプレートにとって意味のある任意の値に設定できます)。また、XML が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26c60-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="26c60-128">CustomData ファイルの XML は、ユーザーが Visual Basic プロジェクトデザイナーの **[マイ拡張**] ページを使用するときに、`My` 拡張機能を含めるように Visual Basic に指示します。</span><span class="sxs-lookup"><span data-stu-id="26c60-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="26c60-129">必要に応じて、CustomData ファイルの XML に <`AssemblyFullName>` 属性を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="26c60-130">これにより、特定のアセンブリへの参照がプロジェクトに追加されたときに、カスタム `My` 拡張機能を自動的にインストールするように Visual Basic に指示します。</span><span class="sxs-lookup"><span data-stu-id="26c60-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="26c60-131">任意のテキストエディターまたは XML エディターを使用して CustomData ファイルを作成し、項目テンプレートの圧縮フォルダー (.zip ファイル) に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="26c60-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="26c60-132">たとえば、次の XML は、CustomData ファイルの内容を示しています。このファイルは、プロジェクトに追加されると、プロジェクト Visual Basic の [My Extensions] フォルダーにテンプレートアイテムが追加されます。</span><span class="sxs-lookup"><span data-stu-id="26c60-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="26c60-133">CustomData ファイルには、次の表に示す属性を持つ <`VBMyExtensionTemplate>` 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26c60-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="26c60-134">属性</span><span class="sxs-lookup"><span data-stu-id="26c60-134">Attribute</span></span>|<span data-ttu-id="26c60-135">説明</span><span class="sxs-lookup"><span data-stu-id="26c60-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="26c60-136">必須。</span><span class="sxs-lookup"><span data-stu-id="26c60-136">Required.</span></span> <span data-ttu-id="26c60-137">拡張機能の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="26c60-137">A unique identifier for the extension.</span></span> <span data-ttu-id="26c60-138">この ID を持つ拡張機能が既にプロジェクトに追加されている場合、ユーザーは再度追加するように求められません。</span><span class="sxs-lookup"><span data-stu-id="26c60-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="26c60-139">必須。</span><span class="sxs-lookup"><span data-stu-id="26c60-139">Required.</span></span> <span data-ttu-id="26c60-140">項目テンプレートのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="26c60-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="26c60-141">省略可。</span><span class="sxs-lookup"><span data-stu-id="26c60-141">Optional.</span></span> <span data-ttu-id="26c60-142">アセンブリ名。</span><span class="sxs-lookup"><span data-stu-id="26c60-142">An assembly name.</span></span> <span data-ttu-id="26c60-143">このアセンブリへの参照がプロジェクトに追加されると、ユーザーは、この項目テンプレートから `My` 拡張機能を追加するように求められます。</span><span class="sxs-lookup"><span data-stu-id="26c60-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="26c60-144">\<CustomDataSignature > 要素を .vstemplate ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="26c60-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="26c60-145">Visual Studio 項目テンプレートを `My` 名前空間拡張として識別するには、項目テンプレートの .vstemplate ファイルも変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c60-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="26c60-146">`<TemplateData>` 要素に `<CustomDataSignature>` 要素を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c60-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="26c60-147">`<CustomDataSignature>` 要素には、次の例に示すように、テキスト `Microsoft.VisualBasic.MyExtension`が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c60-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="26c60-148">圧縮フォルダー (.zip ファイル) 内のファイルを直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="26c60-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="26c60-149">圧縮フォルダーから .vstemplate ファイルをコピーして変更し、圧縮フォルダー内の .vstemplate ファイルを更新したコピーで置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c60-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="26c60-150">次の例は、`<CustomDataSignature>` 要素が追加された .vstemplate ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="26c60-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="26c60-151">テンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="26c60-151">Install the template</span></span>

<span data-ttu-id="26c60-152">テンプレートをインストールするには、圧縮フォルダー ( *.zip*ファイル) を Visual Basic 項目テンプレートフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="26c60-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="26c60-153">既定では、ユーザー項目テンプレートは *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*にあります。</span><span class="sxs-lookup"><span data-stu-id="26c60-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="26c60-154">または、テンプレートを Visual Studio インストーラー ( *.vsi*) ファイルとして発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="26c60-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="26c60-155">参照</span><span class="sxs-lookup"><span data-stu-id="26c60-155">See also</span></span>

- [<span data-ttu-id="26c60-156">Visual Basic における My 名前空間の拡張</span><span class="sxs-lookup"><span data-stu-id="26c60-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="26c60-157">Visual Basic アプリケーション モデルの拡張</span><span class="sxs-lookup"><span data-stu-id="26c60-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="26c60-158">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="26c60-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- <span data-ttu-id="26c60-159">[[マイ拡張] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="26c60-159">[My Extensions Page, Project Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>
