---
title: My.Forms オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350373"
---
# <a name="myforms-object"></a><span data-ttu-id="1f0e8-102">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1f0e8-102">My.Forms Object</span></span>

<span data-ttu-id="1f0e8-103">現在のプロジェクトで宣言されている各 Windows フォームのインスタンスにアクセスするためのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f0e8-104">コメント</span><span class="sxs-lookup"><span data-stu-id="1f0e8-104">Remarks</span></span>

<span data-ttu-id="1f0e8-105">`My.Forms` オブジェクトは、現在のプロジェクトの各フォームのインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="1f0e8-106">プロパティの名前は、プロパティがアクセスするフォームの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="1f0e8-107">`My.Forms` オブジェクトによって提供されるフォームには、修飾子を付けずにフォーム名を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="1f0e8-108">プロパティ名はフォームの型名と同じであるため、既定のインスタンスがあるかのようにフォームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="1f0e8-109">たとえば、`My.Forms.Form1.Show` は、`Form1.Show` と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="1f0e8-110">`My.Forms` オブジェクトは、現在のプロジェクトに関連付けられているフォームのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="1f0e8-111">参照先の Dll で宣言されたフォームへのアクセスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="1f0e8-112">DLL が提供するフォームにアクセスするには、 *DllName*として記述されたフォームの修飾名を使用する必要があります。*FormName*。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="1f0e8-113"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> プロパティを使用して、すべてのアプリケーションの開いているフォームのコレクションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="1f0e8-114">オブジェクトとそのプロパティは、Windows アプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="1f0e8-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-115">Properties</span></span>

<span data-ttu-id="1f0e8-116">`My.Forms` オブジェクトの各プロパティは、現在のプロジェクトのフォームのインスタンスへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="1f0e8-117">プロパティの名前は、プロパティがアクセスするフォームの名前と同じであり、プロパティの型はフォームの型と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="1f0e8-118">名前の競合がある場合、フォームにアクセスするためのプロパティ名は*RootNamespace*_*Namespace*\_*FormName*になります。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="1f0e8-119">たとえば、`Form1.`という名前の2つのフォームを考えてみます。これらのフォームのいずれかがルート名前空間 `WindowsApplication1` であり、名前空間 `Namespace1`では、`My.Forms.WindowsApplication1_Namespace1_Form1`経由でそのフォームにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="1f0e8-120">`My.Forms` オブジェクトを使用すると、起動時に作成されたアプリケーションのメインフォームのインスタンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="1f0e8-121">その他のすべてのフォームでは、`My.Forms` オブジェクトは、アクセス時にフォームの新しいインスタンスを作成して格納します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="1f0e8-122">その後、そのプロパティにアクセスしようとすると、フォームのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="1f0e8-123">フォームのプロパティに `Nothing` を割り当てることによって、フォームを破棄できます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="1f0e8-124">プロパティ setter は、フォームの <xref:System.Windows.Forms.Form.Close%2A> メソッドを呼び出し、格納されている値に `Nothing` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="1f0e8-125">`Nothing` 以外の値をプロパティに割り当てた場合、setter は <xref:System.ArgumentException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="1f0e8-126">`Is` または `IsNot` 演算子を使用して、`My.Forms` オブジェクトのプロパティがフォームのインスタンスを格納するかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="1f0e8-127">これらの演算子を使用すると、プロパティの値が `Nothing`かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="1f0e8-128">通常、`Is` または `IsNot` 演算子は、比較を実行するためにプロパティの値を読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="1f0e8-129">ただし、プロパティが現在 `Nothing`を格納している場合は、プロパティによってフォームの新しいインスタンスが作成され、そのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="1f0e8-130">ただし、Visual Basic コンパイラは、`My.Forms` オブジェクトのプロパティを異なる方法で処理し、`Is` または `IsNot` の演算子が、値を変更せずにプロパティの状態を確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="1f0e8-131">例</span><span class="sxs-lookup"><span data-stu-id="1f0e8-131">Example</span></span>

<span data-ttu-id="1f0e8-132">この例では、既定の `SidebarMenu` フォームのタイトルを変更します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="1f0e8-133">この例を使用するには、プロジェクトに `SidebarMenu`という名前のフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="1f0e8-134">このコードは、Windows アプリケーションプロジェクトでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1f0e8-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f0e8-135">要件</span><span class="sxs-lookup"><span data-stu-id="1f0e8-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="1f0e8-136">プロジェクトの種類別の可用性</span><span class="sxs-lookup"><span data-stu-id="1f0e8-136">Availability by Project Type</span></span>

|<span data-ttu-id="1f0e8-137">プロジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="1f0e8-137">Project type</span></span>|<span data-ttu-id="1f0e8-138">利用可能</span><span class="sxs-lookup"><span data-stu-id="1f0e8-138">Available</span></span>|
|---|---|
|<span data-ttu-id="1f0e8-139">Windows アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1f0e8-139">Windows Application</span></span>|<span data-ttu-id="1f0e8-140">**はい**</span><span class="sxs-lookup"><span data-stu-id="1f0e8-140">**Yes**</span></span>|
|<span data-ttu-id="1f0e8-141">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-141">Class Library</span></span>|<span data-ttu-id="1f0e8-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-142">No</span></span>|
|<span data-ttu-id="1f0e8-143">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1f0e8-143">Console Application</span></span>|<span data-ttu-id="1f0e8-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-144">No</span></span>|
|<span data-ttu-id="1f0e8-145">Windows コントロールライブラリ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-145">Windows Control Library</span></span>|<span data-ttu-id="1f0e8-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-146">No</span></span>|
|<span data-ttu-id="1f0e8-147">Web コントロールライブラリ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-147">Web Control Library</span></span>|<span data-ttu-id="1f0e8-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-148">No</span></span>|
|<span data-ttu-id="1f0e8-149">Windows サービス</span><span class="sxs-lookup"><span data-stu-id="1f0e8-149">Windows Service</span></span>|<span data-ttu-id="1f0e8-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-150">No</span></span>|
|<span data-ttu-id="1f0e8-151">Web サイト</span><span class="sxs-lookup"><span data-stu-id="1f0e8-151">Web Site</span></span>|<span data-ttu-id="1f0e8-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f0e8-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="1f0e8-153">参照</span><span class="sxs-lookup"><span data-stu-id="1f0e8-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="1f0e8-154">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1f0e8-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="1f0e8-155">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="1f0e8-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="1f0e8-156">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="1f0e8-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="1f0e8-157">アプリケーション フォームへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1f0e8-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
