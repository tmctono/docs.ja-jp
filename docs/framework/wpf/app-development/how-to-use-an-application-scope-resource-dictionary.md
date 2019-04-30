---
title: '方法: アプリケーション スコープのリソース ディクショナリを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 589e28b3c05496e3fc17055b98240e389faed068
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007488"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="dae43-102">方法: アプリケーション スコープのリソース ディクショナリを使用する</span><span class="sxs-lookup"><span data-stu-id="dae43-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="dae43-103">この例では、アプリケーション スコープのカスタム リソース ディクショナリを定義して、使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dae43-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dae43-104">例</span><span class="sxs-lookup"><span data-stu-id="dae43-104">Example</span></span>  
 <span data-ttu-id="dae43-105"><xref:System.Windows.Application> 共有リソースのアプリケーション スコープ ストアを公開します:<xref:System.Windows.Application.Resources%2A>します。</span><span class="sxs-lookup"><span data-stu-id="dae43-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="dae43-106">既定で、<xref:System.Windows.Application.Resources%2A>プロパティがのインスタンスで初期化されて、<xref:System.Windows.ResourceDictionary>型。</span><span class="sxs-lookup"><span data-stu-id="dae43-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="dae43-107">Get を使用してアプリケーション スコープのプロパティを設定すると、このインスタンスを使用する<xref:System.Windows.Application.Resources%2A>します。</span><span class="sxs-lookup"><span data-stu-id="dae43-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="dae43-108">詳細については、「[方法 :取得および設定、アプリケーション スコープ リソース](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="dae43-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="dae43-109">使用して設定する複数のリソースがある場合<xref:System.Windows.Application.Resources%2A>、カスタム リソース ディクショナリは、これらのリソースを格納し、設定する代わりに使用できます<xref:System.Windows.Application.Resources%2A>を代わりにします。</span><span class="sxs-lookup"><span data-stu-id="dae43-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="dae43-110">XAML を使用してカスタム リソース ディクショナリを宣言する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dae43-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="dae43-111">使用して全体のリソース ディクショナリのスワップ<xref:System.Windows.Application.Resources%2A>各テーマが 1 つのリソース ディクショナリでカプセル化、アプリケーション スコープのテーマをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="dae43-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="dae43-112"><xref:System.Windows.ResourceDictionary> を設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="dae43-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="dae43-113">によって公開されているリソース ディクショナリからアプリケーション スコープのリソースを取得する方法を次に示します<xref:System.Windows.Application.Resources%2A>XAML でします。</span><span class="sxs-lookup"><span data-stu-id="dae43-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="dae43-114">コードでリソースも取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dae43-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="dae43-115">使用するときに 2 つの考慮事項があります<xref:System.Windows.Application.Resources%2A>します。</span><span class="sxs-lookup"><span data-stu-id="dae43-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="dae43-116">まず、ディクショナリ*キー*オブジェクトは両方の設定とプロパティ値を取得するときに正確に同じオブジェクト インスタンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae43-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="dae43-117">(キーに文字列を使用する場合、大文字と小文字が区別されることに注意してください)。2 つ目は、ディクショナリ*値*オブジェクトはプロパティ値を取得するときに、目的の型に値を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae43-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae43-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dae43-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="dae43-119">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="dae43-119">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="dae43-120">マージされたリソース ディクショナリ</span><span class="sxs-lookup"><span data-stu-id="dae43-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
