---
title: My.Resources オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 7f5d81194123ad2151a494a3cb79aa1955e0fdad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350327"
---
# <a name="myresources-object"></a><span data-ttu-id="92f2e-102">My.Resources オブジェクト</span><span class="sxs-lookup"><span data-stu-id="92f2e-102">My.Resources Object</span></span>
<span data-ttu-id="92f2e-103">アプリケーションのリソースにアクセスするためのプロパティとクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92f2e-104">コメント</span><span class="sxs-lookup"><span data-stu-id="92f2e-104">Remarks</span></span>  
 <span data-ttu-id="92f2e-105">`My.Resources` オブジェクトは、アプリケーションのリソースへのアクセスを提供し、アプリケーションのリソースを動的に取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="92f2e-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="92f2e-106">詳細については、「[アプリケーションリソースの管理 (.net)](/visualstudio/ide/managing-application-resources-dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f2e-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="92f2e-107">`My.Resources` オブジェクトは、グローバルリソースのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="92f2e-108">フォームに関連付けられたリソースファイルへのアクセスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="92f2e-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="92f2e-109">フォームリソースには、フォームからアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f2e-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="92f2e-110">`My.Resources` オブジェクトから、アプリケーションのカルチャ固有のリソースファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="92f2e-111">既定では、`My.Resources` オブジェクトは、<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> プロパティのカルチャに一致するリソースファイルからリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="92f2e-112">ただし、この動作をオーバーライドして、リソースに使用する特定のカルチャを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="92f2e-113">詳細については、「[デスクトップ アプリケーションのリソース](../../../framework/resources/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f2e-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="92f2e-114">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="92f2e-114">Properties</span></span>  
 <span data-ttu-id="92f2e-115">`My.Resources` オブジェクトのプロパティは、アプリケーションのリソースへの読み取り専用アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="92f2e-116">リソースを追加または削除するには、**プロジェクトデザイナー**を使用します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="92f2e-117">**プロジェクトデザイナー**によって追加されたリソースにアクセスするには *、`My.Resources.`リソースを使用します*。</span><span class="sxs-lookup"><span data-stu-id="92f2e-117">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="92f2e-118">また、**ソリューションエクスプローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[新しい項目の追加]** または **[既存項目の追加]** をクリックして、リソースファイルを追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="92f2e-119">この方法で追加されたリソースにアクセスするには、`My.Resources.`*Resourcefilename* *`.`を使用します*。</span><span class="sxs-lookup"><span data-stu-id="92f2e-119">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="92f2e-120">各リソースには名前、カテゴリ、および値があり、これらのリソースの設定によって、リソースにアクセスするためのプロパティが `My.Resources` オブジェクトにどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="92f2e-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="92f2e-121">**プロジェクトデザイナー**に追加されたリソースの場合:</span><span class="sxs-lookup"><span data-stu-id="92f2e-121">For resources added in the **Project Designer**:</span></span>  
  
- <span data-ttu-id="92f2e-122">名前によって、プロパティの名前が決まります。</span><span class="sxs-lookup"><span data-stu-id="92f2e-122">The name determines the name of the property,</span></span>  
  
- <span data-ttu-id="92f2e-123">リソースデータはプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-123">The resource data is the value of the property,</span></span>  
  
- <span data-ttu-id="92f2e-124">カテゴリによって、プロパティの種類が決まります。</span><span class="sxs-lookup"><span data-stu-id="92f2e-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="92f2e-125">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="92f2e-125">Category</span></span>|<span data-ttu-id="92f2e-126">プロパティのデータ型</span><span class="sxs-lookup"><span data-stu-id="92f2e-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="92f2e-127">**文字列**</span><span class="sxs-lookup"><span data-stu-id="92f2e-127">**Strings**</span></span>|[<span data-ttu-id="92f2e-128">String</span><span class="sxs-lookup"><span data-stu-id="92f2e-128">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="92f2e-129">**イメージ**</span><span class="sxs-lookup"><span data-stu-id="92f2e-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="92f2e-130">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="92f2e-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="92f2e-131">**オーディオ**</span><span class="sxs-lookup"><span data-stu-id="92f2e-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="92f2e-132"><xref:System.IO.UnmanagedMemoryStream> クラスは <xref:System.IO.Stream> クラスから派生するので、<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> メソッドなどのストリームを受け取るメソッドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="92f2e-133">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="92f2e-133">**Files**</span></span>|<span data-ttu-id="92f2e-134">テキストファイルの[文字列](../../../visual-basic/language-reference/data-types/string-data-type.md)を -   します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-134">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="92f2e-135">イメージファイルの <xref:System.Drawing.Bitmap> を -   します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="92f2e-136">アイコンファイルの <xref:System.Drawing.Icon> を -   します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="92f2e-137">サウンドファイルの <xref:System.IO.UnmanagedMemoryStream> を -   します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="92f2e-138">**その他**</span><span class="sxs-lookup"><span data-stu-id="92f2e-138">**Other**</span></span>|<span data-ttu-id="92f2e-139">デザイナーの**Type**列の情報によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="92f2e-140">クラス</span><span class="sxs-lookup"><span data-stu-id="92f2e-140">Classes</span></span>  
 <span data-ttu-id="92f2e-141">`My.Resources` オブジェクトは、各リソースファイルを共有プロパティを持つクラスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="92f2e-142">クラス名は、リソースファイルの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="92f2e-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="92f2e-143">前のセクションで説明したように、リソースファイル内のリソースはクラスのプロパティとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92f2e-144">例</span><span class="sxs-lookup"><span data-stu-id="92f2e-144">Example</span></span>  
 <span data-ttu-id="92f2e-145">この例では、フォームのタイトルを、アプリケーションリソースファイル内の `Form1Title` という名前の文字列リソースに設定します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="92f2e-146">この例を使用するには、アプリケーションのリソースファイルに `Form1Title` という名前の文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="92f2e-147">例</span><span class="sxs-lookup"><span data-stu-id="92f2e-147">Example</span></span>  
 <span data-ttu-id="92f2e-148">この例では、フォームのアイコンを、アプリケーションのリソースファイルに格納されている `Form1Icon` という名前のアイコンに設定します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="92f2e-149">この例を使用するには、アプリケーションのリソースファイルに `Form1Icon` という名前のアイコンが必要です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="92f2e-150">例</span><span class="sxs-lookup"><span data-stu-id="92f2e-150">Example</span></span>  
 <span data-ttu-id="92f2e-151">この例では、フォームの背景画像を、アプリケーションリソースファイル内の `Form1Background`という名前のイメージリソースに設定します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="92f2e-152">この例を使用するには、アプリケーションのリソースファイルに `Form1Background` という名前のイメージリソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="92f2e-153">例</span><span class="sxs-lookup"><span data-stu-id="92f2e-153">Example</span></span>  
 <span data-ttu-id="92f2e-154">この例では、アプリケーションのリソースファイルに `Form1Greeting` という名前のオーディオリソースとして格納されているサウンドを再生します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="92f2e-155">この例を使用するには、アプリケーションのリソースファイルに `Form1Greeting` という名前のオーディオリソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="92f2e-156">`My.Computer.Audio.Play` メソッドは、Windows フォームアプリケーションに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="92f2e-157">例</span><span class="sxs-lookup"><span data-stu-id="92f2e-157">Example</span></span>  
 <span data-ttu-id="92f2e-158">この例では、アプリケーションの文字列リソースのフランス語カルチャバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="92f2e-159">リソースには `Message`という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="92f2e-159">The resource is named `Message`.</span></span> <span data-ttu-id="92f2e-160">`My.Resources` オブジェクトが使用するカルチャを変更するために、この例では <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>を使用します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="92f2e-161">この例を使用するには、アプリケーションのリソースファイルに `Message` という名前の文字列が必要です。また、アプリケーションには、そのリソースファイル Resources.fr のフランス語カルチャバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="92f2e-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="92f2e-162">アプリケーションにフランス語カルチャバージョンのリソースファイルがない場合、`My.Resource` オブジェクトは、既定のカルチャリソースファイルからリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="92f2e-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="92f2e-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="92f2e-163">See also</span></span>

- [<span data-ttu-id="92f2e-164">アプリケーション リソースの管理 (.NET)</span><span class="sxs-lookup"><span data-stu-id="92f2e-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="92f2e-165">デスクトップ アプリケーションのリソース</span><span class="sxs-lookup"><span data-stu-id="92f2e-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
