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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b53be90764c6537fb27cb1b5ed781a68e69effa0
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504675"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="2c6d5-102">Model-View-View Model を利用した汎用性のあるクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="2c6d5-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="2c6d5-103">.NET Framework を使用して[ポータブル クラス ライブラリ](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)モデル-ビュー-ビュー モデル (MVVM) パターンを実装して、複数のプラットフォームでアセンブリを共有します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="2c6d5-104">MVVM では、基になるビジネス ロジックからユーザー インターフェイスを分離するアプリケーション パターンです。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="2c6d5-105">Visual Studio 2012 のポータブル クラス ライブラリ プロジェクトでモデルとビュー モデル クラスを実装し、さまざまなプラットフォーム用にカスタマイズされたビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="2c6d5-106">このアプローチでは、データを記述できます。 モデルとビジネス ロジックを 1 回だけ、.NET Framework、Silverlight、Windows Phone のコードを使用および[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリは、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>

 ![プラットフォーム間で共有アセンブリの MVVM を使用したポータブル クラス ライブラリを示します。](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="2c6d5-108">このトピックでは、MVVM パターンに関する一般的な情報は提供されません。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="2c6d5-109">ポータブル クラス ライブラリを使用して、MVVM を実装する方法についての情報を提供するだけです。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="2c6d5-110">MVVM の詳細については、次を参照してください。、 [MVVM クイック スタートで、wpf、Prism ライブラリ 5.0 が使用して](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40))します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="2c6d5-111">MVVM をサポートするクラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="2c6d5-112">.NET Framework 4.5 を対象とする場合[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]Silverlight、またはポータブル クラス ライブラリ プロジェクトの Windows Phone 7.5 次のクラスは、MVVM パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-112">When you target the .NET Framework 4.5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="2c6d5-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> クラス</span><span class="sxs-lookup"><span data-stu-id="2c6d5-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="2c6d5-123">すべてのクラス、<xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>名前空間</span><span class="sxs-lookup"><span data-stu-id="2c6d5-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="2c6d5-124">MVVM の実装</span><span class="sxs-lookup"><span data-stu-id="2c6d5-124">Implementing MVVM</span></span>
 <span data-ttu-id="2c6d5-125">MVVM を実装するには、通常を作成するモデルとビュー モデルの両方でポータブル クラス ライブラリ プロジェクトでは、ポータブル クラス ライブラリ プロジェクトがポータブルでないプロジェクトを参照できないためです。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="2c6d5-126">モデルとビュー モデルは、同じプロジェクト内、または別のプロジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="2c6d5-127">個別のプロジェクトを使用する場合は、モデル プロジェクトにビューのモデル プロジェクトからの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="2c6d5-128">モデルをコンパイルし、モデル プロジェクトを表示すると後、は、ビューを含むアプリでそれらのアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="2c6d5-129">ビューは、ビュー モデルとのみやり取りをする場合のみ、ビュー モデルを含むアセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="2c6d5-130">モデル</span><span class="sxs-lookup"><span data-stu-id="2c6d5-130">Model</span></span>
 <span data-ttu-id="2c6d5-131">次の例では、ポータブル クラス ライブラリ プロジェクトである単純なモデル クラスを示します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="2c6d5-132">次の例では、設定、取得、およびポータブル クラス ライブラリ プロジェクト内のデータを更新する簡単な方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="2c6d5-133">実際のアプリでは、Windows Communication Foundation (WCF) サービスなどのソースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="2c6d5-134">ビュー モデル</span><span class="sxs-lookup"><span data-stu-id="2c6d5-134">View Model</span></span>
 <span data-ttu-id="2c6d5-135">MVVM パターンを実装するときに、ビュー モデルの基本クラスが頻繁に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="2c6d5-136">次の例では、基本クラスを示します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="2c6d5-137">実装、<xref:System.Windows.Input.ICommand>インターフェイスは、MVVM パターンでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="2c6d5-138"><xref:System.Windows.Input.ICommand> インターフェイスを実装する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="2c6d5-139">次の例では、簡略化されたビュー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="2c6d5-140">表示</span><span class="sxs-lookup"><span data-stu-id="2c6d5-140">View</span></span>  
 <span data-ttu-id="2c6d5-141">.NET Framework 4.5 アプリから[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリ、Silverlight ベースのアプリまたは Windows Phone 7.5 アプリの場合は、モデルとビュー モデル プロジェクトを含むアセンブリを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-141">From a .NET Framework 4.5 app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="2c6d5-142">対話するビューを作成するには、ビュー モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="2c6d5-143">取得し、ビュー モデルからデータを更新する Windows Presentation Foundation (WPF) アプリを簡略化されたは、次の例です。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="2c6d5-144">Windows Phone、Silverlight で同様のビューを作成または[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]アプリ。</span><span class="sxs-lookup"><span data-stu-id="2c6d5-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2c6d5-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c6d5-145">See also</span></span>

- [<span data-ttu-id="2c6d5-146">ポータブル クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2c6d5-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
