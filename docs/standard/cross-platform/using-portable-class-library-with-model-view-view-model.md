---
title: Model-View-View Model を利用した汎用性のあるクラス ライブラリの使用
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: ff34b295ba443088115d470d8ade0c986ac1d856
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288850"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="82a74-102">Model-View-View Model を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="82a74-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="82a74-103">.NET Framework[ポータブルクラスライブラリ](cross-platform-development-with-the-portable-class-library.md)を使用して、モデルビュービューモデル (MVVM) パターンを実装し、複数のプラットフォーム間でアセンブリを共有できます。</span><span class="sxs-lookup"><span data-stu-id="82a74-103">You can use the .NET Framework [Portable Class Library](cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="82a74-104">MVVM は、基になるビジネスロジックからユーザーインターフェイスを分離するアプリケーションパターンです。</span><span class="sxs-lookup"><span data-stu-id="82a74-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="82a74-105">Visual Studio 2012 のポータブルクラスライブラリプロジェクトでモデルクラスとビューモデルクラスを実装し、さまざまなプラットフォーム用にカスタマイズされたビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="82a74-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="82a74-106">この方法では、次の図に示すように、データモデルとビジネスロジックを1回だけ記述し、.NET Framework、Silverlight、Windows Phone、Windows 8.x ストアアプリからそのコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82a74-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![プラットフォーム間でアセンブリを共有する MVVM を使用して、ポータブルクラスライブラリを表示します。](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="82a74-108">このトピックでは、MVVM パターンに関する一般的な情報については説明しません。</span><span class="sxs-lookup"><span data-stu-id="82a74-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="82a74-109">ここでは、ポータブルクラスライブラリを使用して MVVM を実装する方法についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="82a74-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="82a74-110">MVVM の詳細については、「 [MVVM クイック5.0 スタート](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82a74-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="82a74-111">MVVM をサポートするクラス</span><span class="sxs-lookup"><span data-stu-id="82a74-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="82a74-112">ポータブルクラスライブラリプロジェクトの .NET Framework 4.5、.NET for Windows 8.x ストアアプリ、Silverlight、Windows Phone 7.5 を対象とする場合は、MVVM パターンを実装するために次のクラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82a74-112">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="82a74-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="82a74-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="82a74-123">名前空間のすべてのクラス <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="82a74-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="82a74-124">MVVM の実装</span><span class="sxs-lookup"><span data-stu-id="82a74-124">Implementing MVVM</span></span>
 <span data-ttu-id="82a74-125">ポータブルクラスライブラリプロジェクトはポータブルでないプロジェクトを参照できないため、MVVM を実装するには、通常、ポータブルクラスライブラリプロジェクトでモデルとビューモデルの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="82a74-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="82a74-126">モデルモデルとビューモデルは、同じプロジェクト内にあっても、別のプロジェクトにあってもかまいません。</span><span class="sxs-lookup"><span data-stu-id="82a74-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="82a74-127">個別のプロジェクトを使用する場合は、ビューモデルプロジェクトからモデルプロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="82a74-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="82a74-128">モデルおよびビューモデルのプロジェクトをコンパイルした後、ビューを含むアプリでこれらのアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="82a74-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="82a74-129">ビューがビューモデルとのみ対話する場合は、ビューモデルを含むアセンブリを参照するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="82a74-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="82a74-130">モデル</span><span class="sxs-lookup"><span data-stu-id="82a74-130">Model</span></span>
 <span data-ttu-id="82a74-131">次の例は、ポータブルクラスライブラリプロジェクトに存在する可能性がある簡略化されたモデルクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="82a74-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="82a74-132">次の例は、ポータブルクラスライブラリプロジェクトのデータを設定、取得、および更新する簡単な方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82a74-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="82a74-133">実際のアプリでは、Windows Communication Foundation (WCF) サービスなどのソースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="82a74-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="82a74-134">モデルの表示</span><span class="sxs-lookup"><span data-stu-id="82a74-134">View Model</span></span>
 <span data-ttu-id="82a74-135">ビューモデルの基本クラスは、MVVM パターンを実装するときに頻繁に追加されます。</span><span class="sxs-lookup"><span data-stu-id="82a74-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="82a74-136">基底クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="82a74-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="82a74-137">インターフェイスの実装 <xref:System.Windows.Input.ICommand> は、MVVM パターンでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="82a74-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="82a74-138"><xref:System.Windows.Input.ICommand> インターフェイスを実装する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="82a74-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="82a74-139">次の例は、簡略化されたビューモデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="82a74-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="82a74-140">表示</span><span class="sxs-lookup"><span data-stu-id="82a74-140">View</span></span>  
 <span data-ttu-id="82a74-141">.NET Framework 4.5 アプリ、Windows 8.x ストアアプリ、Silverlight ベースのアプリ、または Windows Phone 7.5 アプリから、モデルプロジェクトとビューモデルプロジェクトを含むアセンブリを参照できます。</span><span class="sxs-lookup"><span data-stu-id="82a74-141">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="82a74-142">次に、ビューモデルと対話するビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="82a74-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="82a74-143">次の例は、ビューモデルからデータを取得して更新する簡素化された Windows Presentation Foundation (WPF) アプリを示しています。</span><span class="sxs-lookup"><span data-stu-id="82a74-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="82a74-144">Silverlight、Windows Phone、または Windows 8.x ストアアプリでも同様のビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="82a74-144">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="82a74-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="82a74-145">See also</span></span>

- [<span data-ttu-id="82a74-146">ポータブル クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="82a74-146">Portable Class Library</span></span>](cross-platform-development-with-the-portable-class-library.md)
