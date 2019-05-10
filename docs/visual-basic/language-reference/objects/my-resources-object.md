---
title: My.Resources オブジェクト (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 02e29b17404da0e868973364b0b17b5c4ca418c6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647626"
---
# <a name="myresources-object"></a><span data-ttu-id="a7d59-102">My.Resources オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a7d59-102">My.Resources Object</span></span>
<span data-ttu-id="a7d59-103">アプリケーションのリソースにアクセスするためのプロパティとクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7d59-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7d59-104">Remarks</span></span>  
 <span data-ttu-id="a7d59-105">`My.Resources`オブジェクト、アプリケーションのリソースへのアクセスを提供でき、動的にアプリケーションのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="a7d59-106">詳細については、次を参照してください。[アプリケーション リソースの管理 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="a7d59-107">`My.Resources`オブジェクトはグローバル リソースのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="a7d59-108">フォームに関連付けられているリソース ファイルへのアクセスは行いません。</span><span class="sxs-lookup"><span data-stu-id="a7d59-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="a7d59-109">フォームのフォーム リソースにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7d59-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="a7d59-110">アプリケーションのカルチャ固有のリソース ファイルにアクセスすることができます、`My.Resources`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a7d59-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="a7d59-111">既定で、`My.Resources`オブジェクトのカルチャに一致するリソース ファイルからリソースを調べ、<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a7d59-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="a7d59-112">ただし、この動作をオーバーライドし、リソースに使用する特定のカルチャを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a7d59-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="a7d59-113">詳細については、「[デスクトップ アプリケーションのリソース](../../../framework/resources/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7d59-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a7d59-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a7d59-114">Properties</span></span>  
 <span data-ttu-id="a7d59-115">プロパティ、`My.Resources`オブジェクトは、アプリケーションのリソースへの読み取り専用アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="a7d59-116">を追加または削除のリソースを使用して、**プロジェクト デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="a7d59-117">使用して追加のリソースにアクセスすることができます、**プロジェクト デザイナー**を使用して`My.Resources.` *resourceName*します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-117">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="a7d59-118">追加またはでプロジェクトを選択してリソース ファイルを削除することができますも**ソリューション エクスプ ローラー**クリック**新しい項目の追加**または**既存項目の追加**から、 **プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="a7d59-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="a7d59-119">使用して、この方法で追加のリソースにアクセスすることができます`My.Resources.` *resourceFileName*`.`*resourceName*します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-119">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="a7d59-120">各リソースには、名前、カテゴリ、および値、およびこれらのリソースの設定は、リソースにアクセスするプロパティを表示する方法を決定、`My.Resources`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a7d59-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="a7d59-121">追加するリソースの**プロジェクト デザイナー**:</span><span class="sxs-lookup"><span data-stu-id="a7d59-121">For resources added in the **Project Designer**:</span></span>  
  
- <span data-ttu-id="a7d59-122">名前は、プロパティの名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-122">The name determines the name of the property,</span></span>  
  
- <span data-ttu-id="a7d59-123">リソース データは、プロパティの値</span><span class="sxs-lookup"><span data-stu-id="a7d59-123">The resource data is the value of the property,</span></span>  
  
- <span data-ttu-id="a7d59-124">カテゴリは、プロパティの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="a7d59-125">Category</span><span class="sxs-lookup"><span data-stu-id="a7d59-125">Category</span></span>|<span data-ttu-id="a7d59-126">プロパティのデータ型</span><span class="sxs-lookup"><span data-stu-id="a7d59-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="a7d59-127">**文字列**</span><span class="sxs-lookup"><span data-stu-id="a7d59-127">**Strings**</span></span>|[<span data-ttu-id="a7d59-128">String</span><span class="sxs-lookup"><span data-stu-id="a7d59-128">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="a7d59-129">**イメージ**</span><span class="sxs-lookup"><span data-stu-id="a7d59-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="a7d59-130">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="a7d59-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="a7d59-131">**オーディオ**</span><span class="sxs-lookup"><span data-stu-id="a7d59-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="a7d59-132"><xref:System.IO.UnmanagedMemoryStream>クラスから派生、<xref:System.IO.Stream>クラス、メソッドなど、ストリームを確認すると、使用できるように、<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a7d59-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="a7d59-133">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="a7d59-133">**Files**</span></span>|<span data-ttu-id="a7d59-134">-   [文字列](../../../visual-basic/language-reference/data-types/string-data-type.md)テキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-134">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="a7d59-135">-   <xref:System.Drawing.Bitmap> イメージ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="a7d59-136">-   <xref:System.Drawing.Icon> アイコン ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="a7d59-137">-   <xref:System.IO.UnmanagedMemoryStream> 音声ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="a7d59-138">**その他**</span><span class="sxs-lookup"><span data-stu-id="a7d59-138">**Other**</span></span>|<span data-ttu-id="a7d59-139">デザイナーの内の情報によって決まります**型**列。</span><span class="sxs-lookup"><span data-stu-id="a7d59-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="a7d59-140">クラス</span><span class="sxs-lookup"><span data-stu-id="a7d59-140">Classes</span></span>  
 <span data-ttu-id="a7d59-141">`My.Resources`オブジェクト クラスと共有のプロパティとして各リソース ファイルを公開します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="a7d59-142">クラス名は、リソース ファイルの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="a7d59-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="a7d59-143">前のセクションで説明した、リソース ファイル内のリソースは、クラスのプロパティとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="a7d59-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7d59-144">例</span><span class="sxs-lookup"><span data-stu-id="a7d59-144">Example</span></span>  
 <span data-ttu-id="a7d59-145">この例では、指定された文字列リソースをフォームのタイトルを設定`Form1Title`アプリケーション リソース ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="a7d59-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="a7d59-146">例を動作させるには、アプリケーションがという名前の文字列をいる必要があります`Form1Title`リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a7d59-147">例</span><span class="sxs-lookup"><span data-stu-id="a7d59-147">Example</span></span>  
 <span data-ttu-id="a7d59-148">この例では、フォームのアイコンを設定するという名前のアイコン`Form1Icon`アプリケーションのリソース ファイルに格納されています。</span><span class="sxs-lookup"><span data-stu-id="a7d59-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="a7d59-149">例を動作させるには、アプリケーションがという名前のアイコンをいる必要があります`Form1Icon`リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="a7d59-150">例</span><span class="sxs-lookup"><span data-stu-id="a7d59-150">Example</span></span>  
 <span data-ttu-id="a7d59-151">この例では、フォームの背景イメージを設定という名前のイメージ リソースを`Form1Background`、アプリケーション リソース ファイルであります。</span><span class="sxs-lookup"><span data-stu-id="a7d59-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="a7d59-152">この例を動作させるには、アプリケーションがという名前のイメージ リソースを必要`Form1Background`リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a7d59-153">例</span><span class="sxs-lookup"><span data-stu-id="a7d59-153">Example</span></span>  
 <span data-ttu-id="a7d59-154">この例は、オーディオという名前のリソースとして格納されているサウンドを再生`Form1Greeting`でアプリケーションのリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="a7d59-155">例を動作させるには、アプリケーションにオーディオという名前のリソースが必要`Form1Greeting`リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="a7d59-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="a7d59-156">`My.Computer.Audio.Play`メソッドは Windows フォーム アプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7d59-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a7d59-157">例</span><span class="sxs-lookup"><span data-stu-id="a7d59-157">Example</span></span>  
 <span data-ttu-id="a7d59-158">この例では、アプリケーションの文字列リソースのフランス語のカルチャのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="a7d59-159">リソースが名前付き`Message`します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-159">The resource is named `Message`.</span></span> <span data-ttu-id="a7d59-160">カルチャを変更するが、`My.Resources`オブジェクトを使用して、この例では<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="a7d59-161">この例を動作させるには、アプリケーションがという名前の文字列をいる必要があります`Message`でのリソース ファイル、およびアプリケーションが必要にリソース ファイルで、Resources.fr-fr.resx のフランス語のカルチャのバージョン。</span><span class="sxs-lookup"><span data-stu-id="a7d59-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="a7d59-162">アプリケーションには、リソース ファイルのフランス語のカルチャのバージョンがない場合、`My.Resource`オブジェクトは、既定のカルチャのリソース ファイルからリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7d59-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a7d59-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7d59-163">See also</span></span>

- [<span data-ttu-id="a7d59-164">アプリケーション リソースの管理 (.NET)</span><span class="sxs-lookup"><span data-stu-id="a7d59-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="a7d59-165">デスクトップ アプリケーションのリソース</span><span class="sxs-lookup"><span data-stu-id="a7d59-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
